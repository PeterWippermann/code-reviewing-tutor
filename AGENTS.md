# AGENTS.md

## Scope

These instructions apply to this directory and all of its subdirectories. A nested `AGENTS.md` may define more specific rules for its subtree.

## Repository mission

This repository develops the **CoRT (Code-reviewing Tutor)** MVP for onboarding new joiners.

Despite its product name, the coach does not review code or pull requests. It uses good, functional, often AI-generated code as learning material and asks new joiners targeted understanding questions in their IDE. Its purpose is to help learners explain control flow, data flow, contracts, abstractions, framework mechanisms, tests, and design decisions—not to judge or change code.

## Authoritative sources

Before changing product behavior, read:

1. `SKILL.md` — authoritative specification for coaching behavior and output formats.
2. `references/curriculum.md` — the living curriculum, defining learning objectives and recording their current understanding depth.
3. `agents/openai.yaml` — presentation and activation metadata, not a domain specification.
4. Existing product, architecture, and decision documents, where relevant.

Direct user or system instructions override this file. For product behavior, `SKILL.md` is the source of truth unless an explicit documented product decision replaces it.

## Non-negotiable product decisions

- Treat existing functional code as learning material and normally assume AI-generated code is correct and appropriate.
- Do not create code/PR reviews, comments, findings, severities, issue lists, quality assessments, merge recommendations, or production-release decisions.
- Do not systematically search for bugs, weaknesses, risks, or code smells; do not propose unsolicited refactorings, improvements, or replacement implementations.
- Treat the IDE as the primary product surface.
- Ask exactly one central understanding question at a time, grounded in concrete code, data/control flow, contracts, or framework behavior.
- Prefer relevant objectives from `references/curriculum.md` without forcing an unsuitable objective. Update each objective monotonically after a qualified answer and never revisit an objective at `4/4 – understood and transferred` in later sessions.
- Use `references/curriculum.md` as the living record of objectives and aggregated understanding status. It must not contain answers, snippets, customer data, or conversation history.
- Assume intrinsic motivation; do not add anti-cheating mechanisms. State assumptions and missing context clearly.

Do not add, without a new product decision: an architecture/planning coach, implementation partner, general debugging coach, code/PR reviewer, reflection/career coach, or hidden tests, traps, or surveillance.

## Required learner experience

- Name file, symbol, and line range as precisely as possible; choose a small coherent code excerpt.
- Start with neutral context and exactly one question about behavior, data flow, contracts, abstractions, framework mechanisms, or tests—never errors or quality judgment.
- Adapt the next question to the next useful understanding depth. After an answer, persist only the highest depth actually demonstrated. Explain the mechanism after a serious attempt; reduce the question or explain directly if blocked or explicitly requested.
- Optionally finish each loop with a small verifiable IDE action. Confirm correct reasoning specifically, not mere agreement. At the end, summarize learning gained, never code quality.
- Use the learner's language for user-facing coaching; default to English if it cannot be inferred. Keep code, paths, symbols, and persisted status values stable as specified by `SKILL.md`.

## Development principles

Make the smallest traceable change that fully achieves the requested product outcome. Follow existing repository conventions; do not introduce dependency changes, architectural rewrites, or abstractions without a concrete variation or testing need.

Keep these concerns separate where the architecture permits: IDE/file/Git context; control- and data-flow reconstruction; learning-objective selection and curriculum lookup; one-question generation; answer evaluation and calibration; monotonic learning-progress persistence; output formatting; provider/model integration; and telemetry/persistence. Do not hide product rules such as “one question at a time” or “consider the curriculum” in editor-specific UI logic.

Optimize for IDEs without unnecessarily coupling core logic to a particular editor API. Preserve source locations, symbols, and provenance. Model actions as verifiable IDE steps such as finding references, opening definitions, inspecting callers or tests, or setting a breakpoint. Never claim files, tests, or commands were checked when they were not; code changes are not the coach’s default result.

Treat source code, customer data, tickets, and learning material as potentially confidential. Process or transfer only context required for the current question. Do not log secrets, tokens, personal data, or complete customer data. Prefer structured, minimized, content-free telemetry, and treat the local curriculum as personal development data.

## Workflow for coding agents

1. Read the closest `AGENTS.md`, `SKILL.md`, `references/curriculum.md`, and relevant project documentation.
2. Inspect existing architecture, tests, scripts, and conventions before introducing a pattern.
3. Determine the affected product invariant and smallest meaningful change.
4. Change implementation and tests together.
5. Run available repository-native format, lint, type, unit, and integration checks.
6. Check the change against product boundaries and the IDE experience.
7. Briefly document the result, checks run, limitations, and deliberately unaddressed work.

Do not invent commands, package managers, or frameworks. If the repository has no runnable checks, say so and describe manual verification.

## Tests and documentation

Test changed domain logic. Cover applicable cases: good functional code; control/data flow, contracts, language/framework mechanisms, and meaningful tests; curriculum progress updates; relevant and non-relevant objectives; skipping `4/4`; monotonic progress at exactly demonstrated depth; no progress after incorrect, blocked, or explanation-only responses; aggregated-only persistence and write-access fallback; exactly one question; correct classification, help, reduced questions, and direct explanation; precise source references; absent review/finding/merge/quality output and unsolicited changes; incomplete context; and confidentiality in logs/telemetry. Test state transitions, exclusions, and safety boundaries rather than exact model prose.

Update `SKILL.md` for domain-behavior changes and `agents/openai.yaml` for presentation/activation changes. Maintain objectives in `references/curriculum.md` only as sentence-form bullets with exactly one `Understanding depth` status. Record long-lived architecture decisions in the established decision documentation. Keep examples small, realistic, and free of customer/production data.

## Definition of done

A change is done only when it remains within the understanding-focused MVP; aligns with `SKILL.md` (or intentionally updates it); advances only demonstrated understanding in the curriculum and excludes completed objectives; includes relevant tests and successful available checks; introduces no review, finding, merge, or overall-quality assessment; exposes no confidential data or unsupported success claims; retains IDE usability and precise references; and documents known limitations.

## Pull-request summary

For repository pull requests, state briefly: the user/learning problem solved, visible behavior change, tests/checks run, remaining risks or assumptions, and deliberately excluded out-of-MVP work. This applies to developing the product; it does not mean the product reviews users’ pull requests.
