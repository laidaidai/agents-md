# Writing and maintenance

## Shape the file around decisions

For new files, use the selected bundled baseline as the actual starting text.
It is an exact copy of the author's source document. Fill its Project Entry
Points / 项目入口 section and preserve the remaining policy wording by default.
For existing files, supplement in place and preserve unaffected text exactly.
Keep detailed project information at its existing source and add useful links.

A documentation index says **where** and **when**:

| Topic | Document | Read before |
| --- | --- | --- |
| API compatibility | `docs/api-contract.md` | Changing request or response schemas |
| Tenant isolation | `docs/security.md` | Modifying data access or authorization |

These paths are illustrative. Substitute actual paths; do not create documents
to satisfy a table. Use Markdown links in final output.

Document commands exactly as supported, including working directory and required
services/runtime. Link lengthy setup instructions. Do not invent conventional
commands or label checks a “full gate” without evidence of their scope.

Keep additions compact. Avoid new duplicates, inventories, and tutorials. Do not
shorten the baseline or existing rules merely to reduce tokens. There is no
universal LOC-to-document-length formula. Existing repeated rules are candidates
for a confirmed cleanup, not silent deletion.

## Reuse contract

- Keep baseline paragraphs and table cells verbatim outside project placeholders,
  unless the user confirms a specific adaptation. Use the matching translation
  rather than translating existing English or Chinese wording again.
- Add project-specific exceptions immediately beside the affected rule or in a
  clearly scoped addition. If an exception changes policy, confirm it first.
- List proposed deletions with the exact clause, evidence of inapplicability,
  and the effect of removal. Group them into one short confirmation round.
- An explicit request to remove a named rule or a previously accepted change
  already counts as confirmation; do not ask again.
- If the user does not answer, retain the rule and complete independent additions.
  If importing a baseline clause would contradict target policy, retain target
  policy and hold that baseline clause pending resolution; report the omission.
- Filling placeholders, removing the template's editing instructions, omitting
  empty placeholder-only rows, and correcting a verified command/path are ordinary
  adaptation. They do not need rule-deletion confirmation.
- When tests or commands are absent, report that fact accurately. Never fabricate
  a check to fill a row. With no project-specific facts, preserve the policy
  baseline and omit empty project scaffolding.

## Update without erasing intent

Classify existing content before editing:

- **Current policy/custom guidance:** preserve wording and scope. Lack of code
  evidence does not invalidate policy, including unfamiliar rules.
- **Project facts:** recheck and patch stale facts against current evidence.
- **Apparently obsolete rules:** propose removal with evidence and wait for
  confirmation. Correct stale factual paths/commands directly when unambiguous.
- **Conflicting/uncertain material:** investigate, ask when material, and keep
  unresolved portions unchanged while completing independent edits.

Preserve headings and formatting where useful. Do not introduce managed-section
markers, replace an entire matching heading, or force a template onto a custom
file. Reorganize when requested while preserving policy, original expressions,
and unrelated work. A generic cleanup request does not authorize rule deletion.

Re-read targets before applying edits if they could have changed during
discovery. Preserve concurrent changes; inspect the final diff. Never use
`git reset`, `clean`, or `stash` to simplify document editing.

If no material update is needed, leave the file untouched. Do not add timestamps,
reorder sections, or create cosmetic churn on repeated runs.

## Scope and compatibility

- Shared rules belong at root; local differences belong in the relevant scope.
  Do not replicate the baseline in every package.
- Resolve links from each output file. Package guidance may need `../../docs/`
  links to root contracts.
- Do not edit parent, global, or sibling guidance for package-only requests.
- Hosts load instructions differently. Do not promise identical discovery or
  precedence for every agent.
- Preserve independent `CLAUDE.md` content. The author's seed documents prefer
  a compatibility entrypoint; that preference is not a universal rule. Do not
  replace a tool-specific file with a one-line pointer.
- Resolve actual maintained targets for symlinks or active overrides. Report
  what is loaded versus what was changed when relevant.

## Review and delivery

Trace facts to sources or answers. Ensure no inference became policy merely
through confident wording. Compare retained paragraphs to the selected baseline
or original target. Check each substantive deletion/rewrite against an explicit
answer. Check paths, case, command definitions, scope, and placeholder cleanup.

Do not run project setup/tests just to validate documentation. If applicable
policy or the user requires execution, inspect commands and authorization first.
Report execution separately from definition checks. An environment failure
does not prove the documented command is wrong.

Summarize files, consequential facts, preferences, and unknown/unverified items.
A research report, transcript, or evidence sidecar is not a default output.
