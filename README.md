# teach-skill

English | [한국어](README.ko.md)

An agent skill that helps you practice thinking, solving, and explaining on your own instead of handing your studying to an AI. The AI writes questions, gives hints for the step where you are stuck, and reviews the answers you submit. Reading an answer does not count as understanding it.

Use it for study plans, understanding checks, coding and math problems, interview and presentation practice, review cards, and study notes. It is not a separate learning app or a reminder service.

The skill instructions are in English. Learning conversations follow the learner's language.

## Installation

You need Node.js, `npx`, and an agent that can read skills. The commands below use the [Vercel skills CLI](https://github.com/vercel-labs/skills). `skills@1.7.0`, the version used for verification, requires Node.js `>=22.20.0`.

### Install from GitHub

```bash
npx skills add chonamdoo/teach_skill --skill teach-skill
```

The interactive prompts ask which agents to install for and which install method to use. The default scope is the current project.

To install for a specific agent in the current project:

```bash
# Codex
npx skills add chonamdoo/teach_skill --skill teach-skill --agent codex

# Claude Code
npx skills add chonamdoo/teach_skill --skill teach-skill --agent claude-code
```

To use the skill across projects, add `--global`:

```bash
npx skills add chonamdoo/teach_skill --skill teach-skill --agent codex --global
```

### Install from a local checkout

Run this from the root of this repository. It works without publishing to GitHub.

```bash
npx skills add . --skill teach-skill --agent codex
```

To install into another project, run the command in that project and replace `.` with the path to this repository. For Claude Code, use `--agent claude-code`.

### Check and remove the installation

```bash
# List the skills in this repository without installing
npx skills add . --list

# List Codex skills installed in the current project
npx skills list --agent codex

# List global installations
npx skills list --agent codex --global

# Remove from the current project
npx skills remove teach-skill --agent codex
```

`teach-skill` should appear in the list. Installing the skill does not mean the agent will pick it automatically. Start a new conversation, name the skill together with your learning goal, and check the actual response. If the skill is missing from the list, check which project you ran the command in and whether you used `--global`. If the CLI cannot find the skill on GitHub, check that the repository is published, or install from a local checkout.

## Getting started

Ask your agent something like this:

```text
Let's study SQL with teach-skill.
I know SELECT and WHERE, and I have a data analysis assignment in two weeks.
I can spend 30 minutes a day. Plan the order to learn things in and give me one problem at a time.
```

If your goal or level is unclear, the skill starts with the one question it needs. If you have already given your goal or your work, it moves on instead of asking again.

A typical exchange goes like this:

1. The AI gives you one question or task.
2. You answer or attempt it first.
3. The AI gives feedback on your actual answer, or helps only with the step where you are stuck.
4. You revise, then check yourself on a small problem with different conditions, without help.

For a concept you have never learned, you can get the necessary basics first. The skill also follows requests to explain only or to take a break. It keeps work done after seeing a hint or a solution separate from work done without help.

## Ten roles

Name a role directly, or describe your situation and let the skill choose.

| Role | When to use it | Example request |
| --- | --- | --- |
| Interviewer | Your goal or level is vague | Before teaching me, check my goal and level one question at a time. |
| Mapmaker | You need an order of study | Connect the concepts and practice tasks I need, from what I know to my goal. |
| Explainer | You are stuck while solving | I'm stuck at this step. Give me a hint for this part, not the answer. |
| Socratic questioner | You want to check your understanding | Ask me about reasons or counterexamples, one question at a time. |
| Examiner | You want a test on what you studied | Give me one problem at a time, and raise the difficulty when my answer and reasoning hold up. |
| Checker | You wrote a solution, summary, or code | Point out only real errors or gaps. Don't rewrite the whole thing. |
| Listener | You explain a concept in your own words | Check where my explanation connects ideas wrongly or leaves a concept out. |
| Diagnostician | You keep making the same mistake | Find possible common causes in these wrong answers and give me a problem that tells them apart. |
| Sparring partner | You practice an interview, presentation, or work situation | Question me like an interviewer. I'll time the 30-second limit myself. |
| Clerk | You organize notes, cards, or a schedule | Turn only these notes into an outline and review questions. Don't add new facts. |

## Review and the next conversation

```text
Turn today's wrong answers into new question cards.
Show me only the questions first, and check my answers after I respond.
Also suggest review intervals based on how I did.
```

Review intervals are adjustable suggestions. Making a schedule does not register reminders. To continue in a new conversation, ask for a record like this and copy it:

```text
Make a checkpoint I can paste into the next conversation.
Include the goal, what was actually checked, whether I used help, what is still unchecked, and the next question.
```

## Scope and limits

- The skill applies to learning conversations. It does not turn ordinary coding or document writing into a quiz.
- You think first by default. You can ask for a full worked solution, and if you explicitly leave learning mode, the request is handled as a normal one.
- AI feedback is not always right. The skill separates agreement with material you supplied, explanations from model knowledge, and actual checks against external sources. It does not claim a check without the source, search, or execution tools to make it.
- Time is handled only as actually measured or as you report it. The skill does not remember across sessions or contact you on its own.
- The skill is a set of behavioral instructions. It is not a security control that restricts the agent's tool permissions.
- It does not guarantee a retention rate, better long-term memory, or passing an exam. The 40% and 61% figures in the supplied slides are not used as this skill's results, because the original study and its conditions could not be verified.
- The 30-second answer time and the 7/10 score in the supplied slides are example values. The skill does not use them as a default time limit or grading standard.

## What's in this repository

| Path | Contents |
| --- | --- |
| [skills/teach-skill/SKILL.md](skills/teach-skill/SKILL.md) | Skill entrypoint: when the skill applies and the shared conversation rules. |
| [skills/teach-skill/references/roles.md](skills/teach-skill/references/roles.md) | Procedures for the ten roles, review cards, and checkpoints. |
| [skills/teach-skill/references/sources.md](skills/teach-skill/references/sources.md) | Design basis, separating what the supplied material says from the author's design decisions. |
| [evals/rubric.md](evals/rubric.md) | Evaluation criteria: required behavior, conditions and exceptions, failures that a score cannot offset, and how each kind of evidence is judged. |
| [evals/](evals/) | Test cases, recorded responses with per-criterion judgments, review records, and installation checks. |
| [docs/english-review.md](docs/english-review.md) | Adversarial evaluation of the English version: per-criterion sub-agent reviews, fixes, and actual runs (in Korean). |
| [docs/claude-code-review.md](docs/claude-code-review.md) | Rubric evaluation in Claude Code: two runs per input, a paired no-skill baseline, and blinded sub-agent judging (in Korean). |
| [docs/design-review.md](docs/design-review.md) | History of the first Korean version: review findings, fixes, evidence, and unverified scope (in Korean). |

Only `skills/teach-skill/` is installed. `evals/` and `docs/` are evaluation records.

The first Korean version's records of 26 inputs and a three-turn conversation are kept as history. The English version was run separately on 24 single inputs and a six-turn conversation built from its actual responses. In an isolated project, copied installs for Codex and Claude Code were checked together with their reference files, and the installed skill was invoked explicitly in Codex. A later Claude Code evaluation ran each input twice with and without the skill, using one pinned model and blinded sub-agent judges; see [docs/claude-code-review.md](docs/claude-code-review.md). Stability across models and human learning outcomes were not tested. The English-version evaluation record has the detailed conditions and actual responses.

You do not need the authoring tools `work-to-skill` or `write-for-work` to use this package.
