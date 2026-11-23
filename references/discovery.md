# Evidence-led discovery

## Read in useful layers

1. **Scope and policy:** applicable `AGENTS.md`, overrides, relevant `CLAUDE.md`,
   contribution rules, worktree status, and package boundaries.
2. **Entrypoints:** README, manifests, workspace configuration, runtime version
   files, task runners, build configuration, and CI definitions.
3. **Intent and contracts:** architecture/design docs, ADRs, specifications,
   schemas, compatibility commitments, security/data rules, and runbooks.
4. **Implementation:** entrypoints, important callers, public interfaces, tests,
   and generated-file headers. Trace enough to verify the specific boundary
   or responsibility you plan to document.

Prefer `rg --files --hidden` with explicit exclusions or a host search tool;
respect ignored paths. Include relevant hidden folders such as `.github` and
existing rule folders without opening credential stores. Avoid unbounded
recursive content dumps. Report inaccessible or skipped areas rather than
asserting they do not exist.

Do not read `.env` values, keys, credentials, database dumps, customer data, or
production logs. Obtain configuration **names and setup-document paths** from
public schemas or clearly sanitized examples. A suggestive filename does not
prove contents are sanitized. Read linked external material only when needed
and within the task's authorization.

## What to discover

| Information | Useful evidence | What not to infer |
| --- | --- | --- |
| Purpose/non-goals | README, product specification, accepted design decisions | Roadmap from folder names |
| Module responsibilities | Workspace manifests, exports, routes, callers | Every folder is a service |
| Runtime/package manager | Version files, manifests, CI, lockfile identity | A lockfile settles competing managers |
| Commands | Task definitions, scripts, CI steps and working directories | Conventional test/lint/build scripts exist |
| Product/data guarantees | Accepted specs, ADRs, schema contracts, explicit policy | Implementation equals intended policy |
| Generated/read-only paths | Generator config, file headers, documented ownership | All ignored files are generated or disposable |
| Verification | Test config, scripts, CI jobs and service setup | A full gate exists because tests exist |
| Durable records | Existing logs and their maintenance policy | Every project needs a memory folder |
| Preferences | Applicable instructions and user answers | Commit history authorizes future pushes |

Lockfile names and relevant headers can identify tools; do not load entire
lockfiles. Inspect CI reusable workflows, matrices, environment, services, and
conditions when they affect the command. A CI command requiring secrets or
containers may not be a local quick check.

Each command record captures purpose, exact invocation, working directory,
runtime/tool requirements, required local services/configuration, and source.
Omit unsupported rows. Without an aggregated quick/full gate, list relevant
existing checks without inventing an aggregate command.

## Facts, intent, and conflicts

Do not impose “code always wins” or “all documents always win.”

- **Executable now:** scripts/configuration define available commands. If a
  README names a deleted script and its replacement is unambiguous, correct
  the command and report stale documentation.
- **Must remain true:** applicable policy and accepted decisions define intended
  guarantees. Violating implementation is drift, not permission to weaken them.
- **Document authority:** use explicit declarations, accepted/superseded status,
  and scope. Modification time or an ADR filename alone does not prove authority.
  Unresolved material conflicts need a focused question.
- **User preference:** preserve established choices; ask for missing preferences.
  A generic template does not outrank project agreements.

Illustrative working records, not facts about the target:

| Candidate | Evidence | Action |
| --- | --- | --- |
| `pnpm check` at root | Manifest scripts.check and CI job | Write verified definition; no execution claim |
| Preserve invoice IDs | Accepted data contract and legacy migration | Link contract before schema edits |
| npm or pnpm | Competing lockfiles, CI and docs disagree | Inspect scope; ask if still unresolved |
| Always create a commit | Some past commits by an agent | Unsupported authorization; omit |

## Monorepos and unusual projects

Start with workspace declarations and scoped guidance. Root instructions cover
shared contracts and cross-package checks; local files cover actual differences.
Do not create a file per package just because the package exists. A package-only
request does not authorize rewriting parent or sibling guidance.

For non-code projects, discover the real authoring, review, rendering, data, or
export workflow. For empty projects, use established purpose and agreements.
For large projects, prioritize relevant entrypoints and important boundaries;
report consequential unexplored areas.
