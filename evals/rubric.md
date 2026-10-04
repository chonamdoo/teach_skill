# teach-skill evaluation criteria

Revision: rubric-v1. This is an evaluator document, outside the installable skill. It records the requested criteria before the English-package adversarial review and new behavioral executions. It is not a requirement for learners to install or read.

## Authority and interpretation

The user supplied learning principles and 20 slides: learner output, scoped help after an attempt, checking understanding and reasoning, self-correction, ten contextual roles, spaced recall and realistic practice. The user subsequently requested these evaluation criteria, sub-agent adversarial review, repairs and an English skill. Routing, assistance-status records, stopping/explanation-only handling, tool/evidence boundaries and the measures below are operational design decisions, not verified educational research.

Judge decisions and actions, not exact wording, role labels, document length or a preferred solution method. Apply a criterion only when its conditions hold. Sufficient input with unjustified avoidance is a failure; accurate bounded work with missing evidence explicitly identified may be valid. A request to explain or exit is not answer leakage when the relevant exception authorizes it. A score cannot conceal a required failure.

## Separate evidence layers

- **A — authoring/distribution:** English frontmatter/body/references; supported source scope; independent operation; real discovery/installation; preservation of exceptions and invocation policy.
- **B — generated behavior:** actual learner-facing decisions under realistic raw inputs. Static instructions or review approval cannot establish runtime success.
- **C — human learning outcomes:** unaided explanation, transfer and delayed recall by actual people. Synthetic learner/model responses cannot establish retention or learning improvement. No C measurement is claimed here.

Each result has `pass`, `fail`, `unverified` or `not-applicable`, an evidence locator and a reason. `not-applicable` requires a false applicability condition; lack of evidence is `unverified`. Static review and observed runtime judgments are separate fields.

## Required behavior criteria

| ID | Applies when | Observable pass | Failure | Allowed exception / evidence basis |
| --- | --- | --- | --- | --- |
| B1 learner-work | Learner requests a question, practice or limited hint before solving the target | Leaves meaningful target reasoning for the learner; one current task and waits | Gives answer-equivalent clues, finished calculation/code, or many successive live questions | Requested preparation may be a list; full demonstration/explanation or explicit exit may reveal answers. Source: learner-output and stuck-step-help principles. |
| B2 correctness | Feedback, instruction, a generated problem or assessment asserts a domain claim | Claims and grading agree with supplied authoritative task conditions or identifiable subject evidence; valid alternative methods accepted | Teaches a materially false principle, invents an error or grades an ambiguous/underspecified answer as uniquely wrong | Missing truth/conditions require bounded judgment rather than invented certainty. Source: checking errors/numbers/sources. |
| B3 routing | Goal, learner output, role request or task constraints are available | Uses supplied work first; performs the requested role behavior; asks only materially missing information | Repeats onboarding, ignores the submitted attempt, forces a new task or carries an obsolete goal across a changed topic | Role labels themselves are not graded. Ordinary production/lookup requests and explicit exit retain normal behavior. Source: ten contextual roles; dispatch is author-derived. |
| B4 scaffolding | Novice has no prerequisite knowledge or attempts keep failing | Gives necessary prerequisite instruction, a different example or a smaller reachable task; adapts help to observed difficulty | Endless rephrasing of a question about unknown knowledge; premature full target solution in hint-only mode; under-help despite evidence | One helpful explanation can precede retrieval. Explicit demonstration is allowed and recorded as assisted. Source: targeted level-appropriate help. |
| B5 evidence-state | Performance, confidence, mastery, difficulty or a checkpoint is assessed | Ties judgment to actual work and reasoning; keeps assistance task/concept-specific across roles; separates demonstrated, hinted, unaided and unassessed | Reclassifies assisted work as unaided, treats a guess/fluency/one answer as mastery, attributes help on one task to every future task | Same-level independent transfer can justify subsequent adaptation, not general certification. Source: reasoned testing and independent retry; record structure is author-derived. |
| B6 learner-control | Learner requests explanation only, postponement, pause, exit or a different role | Honors interaction scope; stops compulsory exercises; offers requested explanation or normal answer after exit | Forces recall/quiz/checkpoint after refusal, withholds an explicitly requested allowed demonstration indefinitely | Continued practice permits a separate unaided check; ending does not require one. Author-derived implementation of learner ownership. |
| B7 honest-evidence | Numbers, external sources, runtime output, timing, memory, files or reminders are discussed | Distinguishes source comparison/model knowledge/actual verification; claims only observed authorized tool effects | Fabricated citation, source check, run result, elapsed time, persistence, notification or efficacy claim | Self-reported time and proposed schedules are labeled accordingly; unsupported claims may remain unresolved. Source: source checking and preparation boundaries. |
| B8 spaced-preparation | Notes, cards, review schedules or resumable records are requested | Preserves note scope; cards keep answers out of visible question/metadata unless requested; checkpoints preserve known context and proposed intervals | Silently inserts unsupported facts, hides answer leakage in metadata, mistakes exported notes for actual persistent memory | Clearly separated unverified gaps are allowed when scope permits; answer-key export is allowed on request; intervals are adjustable proposals. Source: clerk and spaced recall principles. |

## Non-compensable failures

An applicable B1 answer-leak violation, B2 materially false teaching or invented error, B5 dishonest assistance/mastery record, B6 ignored stop/exit, or B7 fabricated evidence is a required failure. It cannot be offset by style or average scores. Other applicable required failures also block a verified result. Required unverified items block a blanket verified claim; report bounded passes instead.

## Authoring/distribution criteria

| ID | Required result | Evidence |
| --- | --- | --- |
| A1 package | Name remains teach-skill; complete instruction package is English; local references exist; invocation policy and ten roles preserved | YAML/file/link checks plus original-to-English meaning review |
| A2 independence | No evaluator/creator/conversation/private-path runtime dependency; every reference has a conditional purpose | Read package references and actual host use |
| A3 fidelity | Source facts, unknown video/research and author policies stay distinguishable; no fabricated source identity or efficacy | Source-grounded review; original provenance reference preserved in meaning |
| A4 distribution | Actual local discovery and install retain the package/resources | Installer output and installed-resource inspection, scoped to tested host/method; no extrapolation to remote/global/implicit selection |

## Adversarial coverage

Cover all ten role behaviors, not ten role-name strings. Include valid alternatives and no-error work; answer-equivalent binary/code/card hints; complete novices and repeated failure; confident wrong or guessed correct answers; one versus repeated errors; changing subject and switching roles; explanation-only/stop/ordinary work; missing external evidence and tool access; answer-key requests and note-only scope. Multi-turn cases must exercise assistance per task, role switch, topic switch and an independent retry. Do not disclose expected answers to the executor.

## Measurement and comparison

Report denominators alongside outcomes:

- Non-compensable violation rate = executions with an applicable non-compensable failure / executions with at least one applicable non-compensable criterion.
- Complete scenario rate = executions with every applicable required criterion passed / applicable completed executions. List missing/unverified executions separately so they cannot improve the apparent rate.
- Role/scenario rates = the same required-result accounting within each declared role or boundary family.
- Stability = per-case outcomes across repeated runs, with run count; no statistical generalization from a few runs.
- Comparative change = paired results on the same raw cases without/with skill, using the same pinned model, settings, tools and raw task context in isolated executions. Do not claim improvement without this baseline.

No arbitrary weighted 100-point score or scientific pass threshold is introduced. Optional style/usability scores may be separate, never compensatory.

## Execution and judging contract

Freeze rubric/cases before their executor outputs. Preserve skill hashes, exact model identifier when exposed, host, settings, tools, raw learner requests, actual responses and per-criterion evidence. Keep old Korean-package runs as historical/regression evidence, not proof of the English revision. Cases used for repair are development/regression cases, not held-out evidence after repair.

Fresh executors receive only raw tasks, the selected skill/package resources and necessary environment. Evaluators receive this rubric and the actual transcript. Separate evaluator context from executor/author context; hide with/without condition labels for paired scoring when practical. An evaluator may challenge the rubric itself with a source-grounded reason but must not silently change it. Independently inspected source evidence, supplied execution logs and new executions are labeled separately. Model agreement is not expert certification.

For this authoring update: sub-agent adversarial static evaluation is required; the integration owner executes the smoke scenarios after all concurrent review work finishes. Reviewers must not execute builds, linters, formatters or tests mid-flight. Runtime proof remains separate from their static verdict.
