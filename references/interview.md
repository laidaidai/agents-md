# A short, adaptive interview

Close gaps; do not administer a fixed questionnaire. Read the project first,
reuse current-task answers and durable policy, and ask only what changes the
document you will write.

## Choose the next round

Prioritize **material conflicts → hidden constraints → missing preferences**.
Usually ask up to three questions at once. Group related choices to reduce
effort. Offer a recommendation and concrete alternatives. Ask more rounds only
when answers expose another material decision. A well-documented update may
need no questions.

Open with evidence: “I found the commands in the manifest and CI and the API
contract in the design docs. These remaining choices affect the instructions.”
Do not ask the user to repeat the stack or list files you can read.

Interview in the user's language. Document language is a separate choice.
Existing language is a good proposed default; preserve it on updates unless
translation is requested.

## Question bank

Select questions; do not ask this table from top to bottom.

| When unresolved | Ask | Recommended starting point |
| --- | --- | --- |
| First setup: language | “Which language should AGENTS.md use, and should replies use the same language?” | Existing doc language for the file; user's language for replies |
| First setup: baseline | “The baseline uses independent routine choices, checks proportional to risk, and specific authorization for external actions. Any exceptions for this project?” | Keep original clauses unless exceptions are specified |
| First setup: verification | “The baseline selects checks by change risk. Keep that, or does this project require a stricter existing policy?” | Preserve target policy; otherwise keep baseline wording |
| First setup: Git | “Leave changes for review, or follow an established commit/PR workflow? Which workflow?” | Leave changes for review; reuse specific existing authorization |
| Command conflict | “CI uses pnpm but the guide says npm. Is this a scope difference, or is one the current standard?” | Explain evidence; do not guess between valid alternatives |
| Hidden product rules | “Which compatibility, data, or product guarantees must survive even if code suggests an easier change?” | Ask for undocumented invariants or their governing document |
| Authority conflict | “These documents disagree about this behavior. Which is authoritative here?” | Show the specific disagreement and sources |
| Dependency/API policy | “Are there project-specific limits on dependencies, public API changes, or migrations?” | Preserve architecture; avoid invented blanket approval rules |
| Durable records relevant | “Should lasting decisions go into an existing ADR or decision log? Which one?” | Reuse existing records; create none by default |
| Paid/remote tests | “Which checks run locally and which need a separately authorized environment?” | Document prerequisites; do not run external tests during discovery |
| Monorepo scope unclear | “Is this guidance for the current package or the whole repository?” | Current package when invoked there; otherwise requested root |
| Compatibility requested | “Retain tool-specific instructions separately, or add a compatibility entrypoint?” | Preserve existing content and loading semantics |
| Long custom instructions | “Patch stale facts in place, or reorganize while retaining policy?” | Patch unless reorganization is already requested |
| A rule seems inapplicable | “This exact clause appears unnecessary because of this evidence. Keep it, or remove it for this project?” | Retain until the specific deletion is confirmed |

## Example first-time preference round

Adapt this Chinese example only when its preferences remain unresolved:

1. “AGENTS.md 用中文还是英文？现有文档以英文为主，我建议文件用英文、与你沟通用中文。”
2. “底稿默认常规可逆改动自行推进、按风险验证、提交和对外操作沿用具体授权。这些原文是否保留？有例外我会单独补充。”
3. “有没有代码里看不出的产品、兼容性或数据约束需要补充？我会优先链接已有文档。”

Ask hidden domain constraints separately when the project suggests they matter.
Do not force users to invent constraints for trivial projects.

## Use answers precisely

- Persist preferences only when intended for future project work. A one-time
  request does not become permanent policy.
- “Be proactive” does not authorize future production deployment, spending,
  destructive changes, or broad external disclosure.
- “Push this completed document” authorizes that task; it does not imply an
  automatic-push preference for future tasks.
- Reuse established answers unless scope or consequences change.
- With a required answer missing, finish independent work and report the
  specific decision. Preserve disputed existing text. Hold changes that would
  be materially misleading without the answer.
- If optional preferences are skipped or the user requests no questions, keep
  conventions and baseline wording, omit unconfirmed additions, and explain
  defaults actually used. Retain rules proposed for deletion until confirmed.
  Never record silence as consent.
