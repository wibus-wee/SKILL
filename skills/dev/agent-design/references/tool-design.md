# Tool Design & ACI

## The Agent-Computer Interface (ACI)

Tool definitions deserve the same attention as system prompts. The **Agent-Computer Interface** is as important as the Human-Computer Interface.

For each tool, the agent needs to know—from the definition alone, mid-inference:
- **When** to use this tool (vs other tools)
- **What** it does and what it doesn't do
- **What** to expect back (format, success/failure signals)
- **What** the boundaries are (scope, side effects, reversibility)

Parameter names and descriptions should be written for a model reading them during generation, not for a developer browsing an IDE.

### Practical Guidelines

- Write descriptions as if explaining to a capable but uninformed collaborator
- Include example usage, edge cases, and clear boundaries from similar tools
- Make it hard to call the tool incorrectly—adjust parameter design, not just descriptions
- Test how the model actually uses the tool; iterate on the interface, not just the prompt
- Prefer formats close to what the model has seen in training (natural text > exotic schemas)
- Avoid formats with "overhead" (e.g., requiring exact line counts, heavy JSON escaping)

> Concrete example from Anthropic's SWE-bench work: switching from relative to absolute file paths in a coding agent eliminated an entire class of errors—not from prompting, but from tool design alone.

---

## Tool Admission Gate

Before proposing or adding any model-facing tool:

1. **Inventory existing capabilities.** List the tools and native resource types already available to the model.
2. **Attempt direct composition.** Show how the required operation would be performed with those capabilities.
3. **Check the representation.** Ask whether changing how the runtime exposes the resource—a path instead of a digest, or a URL instead of an opaque ID—eliminates the need for a tool.
4. **Identify the new boundary.** State the capability, permission, trust, atomicity, transaction, or domain-invariant boundary that existing tools cannot provide.
5. **Reject aliases.** Do not add the tool if it merely renames, presets, or routes an existing operation.

A proposal for a new tool is incomplete unless it states:

- which existing tools were considered;
- why direct composition is insufficient;
- why a representation change is insufficient;
- what genuinely new boundary the tool adds;
- how its side effects, failures, permissions, and reversibility differ from existing tools.

If none of those differences exist, do not add a tool.

### Prefer Native Substrates

Represent resources using interfaces the agent already knows how to operate:

| Resource | Prefer exposing | Keep internal unless required |
|----------|-----------------|-------------------------------|
| File or generated artifact | Real readable workspace path | Blob digest, CAS ref, storage key |
| Web resource | URL | Fetch-cache key, crawler record ID |
| Process | Existing shell/process handle | Scheduler-internal record ID |
| Git state | Commit, branch, tag, or working-tree path | Object-store implementation details |

Internal identifiers may still be returned as integrity or provenance metadata. They should not become the model's primary handle when a native handle already supports the required operation.

### Capability Alias and Domain-Noun Tool Fallacy

A domain noun does not imply a new capability. `Artifact`, `report`, `snapshot`, and `attachment` may all be files. Do not create `read_artifact`, `read_report`, or `read_snapshot` when the runtime can materialize a readable path and the model already has `read_file`.

Bad:

```text
archive_result -> { artifact_id: "sha256:..." }
read_artifact(artifact_id)
```

Still bad when only renamed:

```text
archive_result -> { path: "/runtime/artifacts/..." }
read_artifact(path)  # duplicates read_file(path)
```

Prefer:

```text
archive_result -> {
  path: "/workspace/.artifacts/run-123/result.json",
  sha256: "..."  # optional integrity metadata
}
read_file(path)
```

The runtime owns materialization, sandbox visibility, integrity checks, and cleanup. The model uses the existing filesystem interface. Add a dedicated artifact tool only when the artifact is not representable or safely accessible through the filesystem—for example, a remote protected object requires a distinct permission boundary or server-side transformation.

---

## Interface Wrapping as Knowledge Displacement

When an agent is expected to use a raw tool but the designer lacks confidence in its judgment, the natural engineering instinct is to wrap that tool in a structured semantic interface:

```
// Instead of:
bash("claude -p 'implement user login in my-project'")

// Designer creates:
start_code_task(repo, goal, constraints)
continue_code_task(task_id, hint)
finalize_code_task(task_id)
```

This is a **knowledge displacement error**. The "how to use this" knowledge that belongs in a Skill gets baked into the interface instead, constraining the possibility space before the agent ever acts.

**Why this is wrong:**
- Strips the agent's ability to compose the tool with other tools in novel ways
- Encodes assumptions about usage that may not hold across contexts
- Every structured wrapper is a frozen decision about what the agent is allowed to want
- Reduces composability: the wrapped interface can only do what its designer anticipated

**The correct separation:**
- **Tools** are raw system boundaries—they expose primitive capabilities without encoding usage assumptions
- **Skills** are knowledge packages—they teach the agent *when* and *how* to wield those primitives

The instinct to wrap is a symptom of distrust in the agent's judgment. The correct response to that distrust is a better Skill, not a narrower interface.

---

## Environment as Ground Truth

An agent's sense of progress must come from actual tool call results—what the environment returned—not from internal prediction or belief about what *should have* happened.

Design agent loops around environmental feedback:
1. **Act** — call a tool
2. **Observe** — read the actual result
3. **Act again** — informed by what actually happened

An agent that maintains an internal "mental model" of the world and trusts it over tool outputs is building on sand. The environment is always authoritative. When a tool returns an unexpected result, that result is the ground truth—not the agent's prior expectation.

This principle also applies to multi-step tasks: don't assume step N succeeded because step N-1 succeeded. Verify from the environment.
