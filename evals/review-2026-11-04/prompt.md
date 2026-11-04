You are an adversarial reviewer of an installable agent skill. Read-only: do not edit files.

Repository: /Users/namdoo/Developer/Aiproject/teach-skill (branch teach-skill/review-2026-11-04, identical to commit 7544c37).

## Review target

The installable package `skills/teach-skill/` (`SKILL.md`, `references/roles.md`, `references/sources.md`). The owner wants to update the package itself this time. Earlier reviews changed only evaluation records.

Context you may read: `README.md`, `evals/rubric.md` (A/B criteria), `docs/claude-code-review.md` and `docs/refine-2026-10-06.md` (observed failures and candidate fixes), `evals/*.json` (cases and raw outputs). The authoring guideline is `/Users/namdoo/.agents/skills/work-to-skill/SKILL.md` and `references/validation.md`.

## Questions

Q1. Four package defects are already recorded as open. For each, decide whether the package should change now. If yes, give exact replacement text. If no, say why.
  1. Tool-less save offers: `roles.md` "Copyable checkpoint" only allows saving when a tool exists, but does not stop offering a save (observed in a 6-turn run).
  2. Paired or numbered sub-questions presented as "one question" (`SKILL.md` step 2; observed in a 6-turn run; evaluators disagreed).
  3. `description` not triggering on session-control requests such as "explanation only" or "stop here" even when the skill name is used (observed 4/4 and 9/9 non-invocation; the base model mostly behaved correctly anyway).
  4. A counterexample inside conceptual feedback determines the answer to the next question (observed 2/3 to 3/3 in `socratic-generic`).

Q2. New behavioral defects in the package text: contradictions between `SKILL.md` and `roles.md`, rules that predictably produce wrong learner-facing behavior, lost exceptions, over-restriction (for example refusing a direct answer the learner legitimately asked for), under-specified triggers, or text that costs context without changing behavior. Cite lines.

Q3. Depth (advisory). Using the work-to-skill depth pass (raw material, instruments, outside check), identify where the package starts from digested inputs, relies on the executor's own judgment as the only check, or states an empirical claim without evidence. Stay within the same capability, users, and action boundary: do not add deliverables, adjacent tasks, or permissions. Mark any proposal that changes required inputs, tool access, effort, or cost as needing owner confirmation.

Q4. Frontmatter and portability: check `name` and `description` against host limits you can verify (for example Anthropic: name max 64 chars, lowercase/hyphen, no `anthropic`/`claude`; description max 1024 chars, no XML tags). State which limits you verified and from where; label unverified limits.

## Rules

- Zero findings is acceptable when nothing is justified. Do not invent defects.
- Prefer evidence already in the repo (observed runs) over hypotheses. Label evidence_type as one of: observed_failure, text_contradiction, contract_conflict, untested_behavioral_hypothesis, depth_gap.
- For every finding give: id, question (Q1-Q4), file and line number(s), verbatim quote, evidence_type, evidence (where in the repo or source), impact_scope (which roles, steps, turns, rubric criteria are affected), benefit_of_change, drawback_or_regression_risk, comparison_with_leaving_unchanged, proposed_replacement_text (exact), priority (must | should | could | reject), confidence 0-1.
- Keep proposed text in English (the package is English-only) and minimal. Do not rewrite unrelated sections. Preserve automatic discovery and existing scope.
- Also list tradeoffs between your proposals if they interact (for example a longer description vs. host limits or over-triggering on ordinary work).

Reply with JSON only:
{"reviewer": string, "no_change_recommended": bool, "findings": [...], "interactions": [short strings], "aligned_points": [short strings], "verified_limits": [short strings], "notes": string}
