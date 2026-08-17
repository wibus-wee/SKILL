---
name: clear-docs-comments
description: Use when creating, reviewing, trimming, or reorganizing technical documentation, architecture and design docs, READMEs, Markdown, API or type contracts, inline code and test comments, prompts, diagnostics, or other user-facing technical text. Rewrite existing documents as coherent artifacts instead of appending disconnected sections, use tables for scannable README maps, establish a navigable path from system design to local code, preserve complete contracts, choose one owner for each fact, add stable links, remove narration and duplication, and validate the final wording.
---

# Clear Technical Documentation and Comments

Make system design navigable from repository-level documentation to local code
contracts. Preserve information that code cannot express, then remove reasoning
transcripts, repetition, and decoration. Treat each document as a maintained
whole, not as a chronological stream of appended updates.

## Scope

Apply this skill to technical prose in repositories, source code, tests, tools,
and user-visible output. Read the repository's local instructions first; they
may define terminology, document ownership, required comment syntax, generated
files, or validation commands.

Do not change source code during a review unless the user explicitly requests
implementation. When the task is documentation-only, keep behavior unchanged.

## Documentation topology

Give each level one clear responsibility. Not every repository needs every
level, but a reader should be able to move from system context to the code that
owns a behavior without searching blindly.

- **Root README or architecture document:** Describe the system purpose,
  boundaries, component map, dependency direction, core flows, and entry points.
- **Module README or package documentation:** Describe local responsibilities,
  inputs and outputs, collaborators, lifecycle, failure behavior, and extension
  points.
- **ADR or design document:** Preserve a decision's context, alternatives,
  tradeoffs, and consequences. Keep historical reasoning here instead of in
  current-state reference text.
- **Declaration and contract comment:** Tell a caller or implementer how to use
  a module, type, function, event, hook, or configuration surface correctly.
- **Implementation comment:** Explain a local invariant, ordering constraint,
  algorithmic choice, workaround, or surprising failure path.
- **Test:** Encode observable behavior and boundaries. Use comments only for
  information the fixture or assertions cannot make clear.

Link between these levels instead of copying the same explanation into each.

## Core principles

### Preserve the complete proposition

Keep every clause a reader needs to use or maintain the subject correctly:

- actor and action;
- condition, timing, ordering, and modality such as must, may, or never;
- ownership, state, lifetime, side effects, and concurrency assumptions;
- failure mode, recovery, consequence, and exception;
- negative guarantees and security or compatibility boundaries.

Shorter is better only when no contract information is lost.

### Explain what code cannot express

Use naming, types, structure, and executable checks first. Add comments for
remaining semantics that are non-obvious or cannot be enforced directly.

Prefer this order:

1. Make names and control flow clear.
2. Express constraints with types and API design.
3. Enforce invariants with assertions, validation, and tests.
4. Comment the rationale, boundary, or consequence that still remains implicit.

Do not use comments to compensate for avoidable complexity. Refactor confusing
code when doing so is within scope; otherwise document the risk without
pretending the comment fixes it.

### Keep one home for each fact

Put a fact in the document or code surface that owns it. Elsewhere, state only
the local contract needed for safe use and link to the owner.

Keep rationale near the decision or boundary that owns it. Keep usage
instructions near the consumer. Keep history in an ADR, changelog, or incident
report. Keep protocol details in the protocol or schema documentation.

### Describe current state

Durable documentation must say how the system works now. Avoid narrating old
implementations, migrations, pull requests, commits, review conversations, or
the path used to discover the answer. Preserve that history only when the
document explicitly owns historical decisions or events.

### Rewrite the document; do not append blindly

Read the complete document before editing it. Find the existing section that
owns the new fact, then modify that section in place. Merge overlapping
sections, rename or reorder headings, update existing tables, and remove stale
or superseded text as needed.

Append a new section only when the subject has no appropriate owner and adding
one improves the document's information architecture. Do not preserve the
sequence in which features, fixes, or explanations were added. The final
document must read as one intentionally structured current-state description,
not as a series of patches.

### Match scope to audience

Identify the subject, audience, and permitted detail before writing. Summarize
direct children by purpose and behavior; move their implementation detail to
their own documentation.

Classify substantial documents when relevant:

- **Tutorial:** An ordered path from prerequisites to an observable result.
- **Reference:** A lookup-oriented description of current behavior in a defined
  scope.
- **Architecture document:** A current system map of boundaries, relationships,
  flows, state, and constraints.
- **Decision record:** A dated explanation of a decision, alternatives, and
  consequences.

Do not mix these modes without an explicit boundary.

## README structure and overview tables

A repository or module README that describes multiple meaningful components,
entry points, or configuration surfaces must include at least one concise
overview table near the beginning. Use the table as a map; use normal prose for
design rationale, invariants, tradeoffs, failure behavior, and operational
notes.

Use this as the default README order, adapting it to the audience:

1. State the purpose and scope in a short opening paragraph.
2. Present the important parts in an overview table.
3. Explain architecture and design in coherent prose.
4. Describe core flows, state, ownership, failure, and recovery where relevant.
5. Provide usage, configuration, extension, and verification instructions needed
   by the intended reader.
6. Link to deeper module documentation, declarations, schemas, tests, and
   decision records.

Prefer this table shape for a codebase or module map:

```markdown
| Area | Location | Responsibility | Key relationships |
| --- | --- | --- | --- |
| Runtime | [`src/runtime`](./src/runtime) | Coordinates application lifecycle. | Owns services and invokes adapters. |
| Storage | [`src/storage`](./src/storage) | Persists durable application state. | Implements ports owned by the runtime. |
```

Adapt the columns to the subject. Useful alternatives include **Component**,
**Entry point**, **Inputs and outputs**, **Depends on**, **Configuration**, and
**Details**. Keep the following constraints:

- Use one row per architecture-level concept, not one row per file.
- Link locations, public entry points, and deeper documentation with stable
  relative links.
- Keep cells concise and independently scannable; move multi-paragraph detail
  below the table.
- Describe responsibility and relationships, not merely names and directory
  paths.
- Keep dynamic status, historical notes, and long design arguments out of the
  overview table unless the README specifically owns that information.
- Update, merge, or replace an existing table when its scope overlaps. Do not
  append another inventory that describes the same concepts differently.

Use additional tables for repeated-field comparisons such as configuration
options, public commands, extension points, or compatibility guarantees. Use
prose, a diagram, or an ordered list when sequence, causality, or rationale is
the important relationship.

## Architecture and design documentation

Select the sections needed to make the design understandable; do not create
empty headings merely to satisfy a template.

- **Purpose and scope:** State the problem, audience, goals, and material
  non-goals.
- **System context:** Identify external actors, services, protocols, and trust
  boundaries.
- **Component map:** Name major components by responsibility rather than listing
  directories. State allowed dependency directions and forbidden shortcuts.
- **Core flows:** Trace important requests, events, or data through their real
  entry points to observable outcomes.
- **State and ownership:** State where state lives, who may mutate it, how it is
  synchronized, and when its lifetime ends.
- **Failure and recovery:** Describe failure sources, propagation, retries,
  rollback, partial success, and recovery guarantees.
- **Extension points:** Show where a maintainer adds a handler, provider, plugin,
  storage backend, or protocol variant without bypassing the architecture.
- **Constraints and tradeoffs:** Record security, compatibility, performance,
  deployment, and operational constraints that materially shape the design.
- **Operations and observability:** When relevant, describe configuration,
  health signals, diagnostics, and safe verification.
- **Navigation:** Link to owning modules, public interfaces, schemas, tests, and
  decision records.

Use a diagram when component relationships, dependency direction, or a state or
event sequence is materially clearer visually. Accompany it with enough prose
that its boundary and consequences remain searchable and accessible.

## Declaration and contract comments

Write declaration comments for information a caller or implementer cannot infer
from the name, signature, types, or local convention. Do not require comments on
every declaration when there is no additional contract to preserve.

### Modules and types

Describe the concept's role, responsibility, valid states, invariants,
ownership, lifetime, concurrency model, and relevant architectural boundary.
Explain relationships between fields when individually valid values can form an
invalid combination.

### Functions and methods

Document the non-obvious parts of the calling contract:

- preconditions and valid input ranges;
- result semantics, including absence and partial results;
- side effects and externally observable ordering;
- ownership, borrowing, retention, and cleanup;
- errors, cancellation, retries, and rollback;
- idempotency, reentrancy, concurrency, and performance traps.

Keep implementation strategy out of a declaration comment unless callers must
rely on it.

### Fields and configuration

Explain units, sentinel values, defaults with surprising effects, valid
combinations, reload behavior, security stance, and compatibility constraints.
Do not restate the field name or type.

### Events, callbacks, and lifecycle hooks

State who invokes them, on which thread or sequence, in what order, how often,
what state is valid during the call, whether arguments remain valid afterward,
and how failures affect the surrounding lifecycle.

Follow the repository's language-specific documentation syntax and symbol-link
conventions. Do not introduce Javadoc-, TSDoc-, rustdoc-, or godoc-specific
ceremony into a language-neutral repository rule.

## Inline implementation comments

Place an implementation comment immediately before the smallest block it
constrains. Explain why the code exists, what must remain true, and what breaks
if a future edit ignores the comment.

Use inline comments for:

- ordering, locking, race, and reentrancy constraints;
- ownership transfers and lifecycle transitions;
- non-obvious guards and impossible-state handling;
- algorithms whose correctness depends on a subtle property;
- protocol, browser, platform, or dependency behavior not visible locally;
- intentional error conversion, suppression, retry, or delayed cleanup;
- compatibility workarounds with a concrete removal condition.

Avoid comments that walk through branches, inventory operations, translate
syntax into prose, or describe a temporary debugging process.

Prefer:

```text
Persist the generation before publishing it. Readers may observe publication
immediately, but must never load an uncommitted generation.
```

Avoid:

```text
Save the generation, then update the active generation.
```

Use trailing end-of-line comments only for short local labels such as a unit,
sentinel, or otherwise unavoidable argument meaning. Put multi-clause rationale
above the relevant block. Prefer a named option, enum, helper, or type over an
argument comment when the API can be improved safely.

## Navigation and traceability

Use links to create a stable path across abstraction boundaries, not to replace
the local contract.

- Use relative repository links for files and documents when supported.
- Prefer symbol references supported by the language's documentation tooling
  over prose-only file locations.
- Link architecture documents to module owners, entry points, schemas, and
  representative tests.
- Link local comments to an ADR or design document for extended rationale.
- Link workarounds and deferred work to the authoritative issue or external
  specification, and state the local impact and removal condition beside the
  code.
- Use descriptive link text that says what the target owns.
- Prefer stable document headings, symbols, or files over branch-relative line
  numbers. Use revision permalinks only when historical evidence is the point.
- Verify that the target is authoritative, accessible to the intended audience,
  and still matches the local statement.

A reader must retain enough information to maintain the local contract if a
linked resource becomes unavailable.

## Surface-specific guidance

- **READMEs:** Give consumers and maintainers a concise overview table followed
  by the appropriate architecture or module prose, configuration semantics,
  entry points, failures, limitations, extension points, verification, and
  links to deeper owners. Do not substitute a directory inventory for
  architecture, and do not append updates without integrating them into the
  existing structure.
- **Tests:** Explain why a fixture, platform accommodation, real entry path, or
  indirect observation is necessary. Do not inventory assertions or narrate the
  test body.
- **Tutorials:** State prerequisites, required actions, the real entry path,
  observable verification, and concise warnings.
- **References:** Define the lookup scope and current behavior. Link to deeper
  owners instead of absorbing their detail.
- **Prompts and visible strings:** Treat wording as behavior. Check the rendered
  or executed result when wording affects users, models, protocols, or snapshots.
- **Diagnostics:** Name the failing subject or path, the violated rule, and the
  correction when the fix is not obvious.
- **Generated documentation:** Update its source and regenerate it rather than
  editing catalogs, snapshots, or generated pages by hand.

## Style rules

- Prefer concise, concrete, professional language over metaphor or persuasion.
- Use explicit actors when responsibility matters.
- Preserve meaningful modal words such as **must**, **may**, and **never**.
- State consequences close to the condition that triggers them.
- Split paragraph walls by semantic unit; one paragraph should carry one main
  idea.
- Use examples to resolve ambiguity, not to repeat the preceding prose.
- Follow repository conventions for terminology, wrapping, links, headings,
  comment syntax, and trailing newlines.

## Common problems to remove

- architecture described only as a directory tree;
- append-only READMEs with repeated updates, overlapping sections, or stale
  explanations;
- missing overview tables when a README describes several architectural parts;
- multiple tables that inventory the same concepts with inconsistent columns or
  terminology;
- happy-path documentation with no failure or recovery model;
- public signatures whose ownership, lifetime, or error semantics require
  guessing;
- code restatement and control-flow narration;
- comments that preserve review history instead of current constraints;
- links with no local explanation or links to unstable line numbers;
- TODOs without an action, owner or issue, and completion condition;
- duplicated rules with slightly different wording;
- unsupported adjectives such as “simple,” “safe,” or “obvious”;
- broad claims that omit conditions or exceptions;
- paragraphs containing several unrelated rules;
- decorative emphasis that does not change behavior.

## Workflow

### Create or substantially rewrite documentation

1. Read applicable local instructions and inspect the code or system being
   documented before making design claims.
2. Read the complete existing document and identify content to keep, replace,
   merge, move, or remove; do not plan additions in isolation.
3. Identify the audience, scope, document type, and owner of each material fact.
4. Sketch the navigation path from system context to modules, declarations,
   implementation constraints, tests, and decision records.
5. Extract the required propositions: actors, actions, conditions, ordering,
   state, ownership, failure, recovery, consequences, and exceptions.
6. Build or update the README overview table before writing detailed design
   prose when the subject has multiple architectural parts.
7. Rewrite the owning sections into the smallest complete architecture or
   contract, linking to deeper owners rather than duplicating them.
8. Add examples or diagrams only where they materially reduce ambiguity.
9. Validate claims against code, configuration, schemas, tests, and generated
   output.

### Review or edit existing documentation

1. Read applicable local instructions and confirm the files in scope.
2. Read each document as a whole and identify append-only growth, repeated
   sections, stale tables, and facts that lack a clear owner.
3. Identify missing architecture, contracts, failure behavior, overview tables,
   or navigation before trimming prose.
4. Find the owning document, module, declaration, boundary, or consumer for each
   fact.
5. Update the existing structure in place: merge overlapping sections and
   tables, reorder content, and move or link misplaced detail.
6. Keep the minimum local contract needed for safe use; remove restatement,
   history, reasoning transcripts, duplicated facts, and decoration.
7. Check neighboring documents and code comments for contradictions or stale
   copies.
8. Validate links, rendering, generated outputs, visible wording, and
   repository-specific formatting.
9. Read the final document from top to bottom and confirm it no longer exposes
   the order in which edits were made.
10. Review the final diff for lost exceptions, weakened modality, accidental
    scope expansion, behavior changes, and unrelated edits.

## Final checklist

- Can a new maintainer move from the system overview to the code that owns each
  important behavior?
- Does each non-trivial README provide one clear overview table without
  duplicating prose or another inventory?
- Was existing content integrated, replaced, moved, or removed instead of
  blindly appended?
- Does the architecture describe responsibilities, dependency direction, core
  flows, state ownership, and meaningful failure behavior?
- Can a caller use each documented API without guessing about timing, lifetime,
  side effects, errors, or exceptions?
- Does every implementation comment explain something the code cannot express?
- Is each fact maintained in one clear home, with stable links from other
  relevant surfaces?
- Do workarounds and TODOs have authoritative context and a removal or completion
  condition?
- Does the documentation describe current behavior and stay within its audience
  and scope?
- Are instructions actionable and verification observable?
- Did the edit remove noise without weakening a guarantee?
