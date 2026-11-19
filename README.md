# Max Studies — Aishka, an independent English study coach

**Public, read-only knowledge pack** for a private ChatGPT tutor in a student's **own** ChatGPT account. First focus: **Cambridge Lower Secondary English (0861), Stage 9** (first-language English, not ESL). The tutor can later be extended to Mathematics and Science.

> **Status:** ready-to-use *instructional pilot* with an original diagnostic and sample lesson. It is **not** an official Cambridge product, an approved full Stage 9 syllabus, or a deployed learning app. The historical Cambridge v2.0 objective index must be checked against the school's current programme.

## Start here

**For the student (English):** [MAX_START_HERE.md](guides/MAX_START_HERE.md)

**For the parent (Russian):** [PARENT_SETUP_RU.md](guides/PARENT_SETUP_RU.md)

**Required persistence:** [GitHub progress sync protocol](docs/PROGRESS_SYNC.md), [current checkpoint](progress/current.json) and [history](progress/history.jsonl). Owner approved **public non-personal statistics**. Automatic write access must still be configured and tested in the student's ChatGPT account.

**To create a ChatGPT plugin:** [PLUGIN_CREATOR_PROMPT.md](PLUGIN_CREATOR_PROMPT.md) — ready to paste into **@plugin-creator** in the student's own account if available. It asks for a **skill-only** plugin with **no GitHub app or other external account connection**.

**Core tutor instructions:** [skills/aishka-tutor/SKILL.md](skills/aishka-tutor/SKILL.md). This is the source for the plugin's teaching behaviour.

## Knowledge files

| File | Purpose |
|---|---|
| [Cambridge Stage 9 overview](curriculum/README.md) | Curriculum version, public sources, scope and copyright |
| [Stage 9 objective code index](curriculum/STAGE9_OBJECTIVES.csv) | 67 identifiers and our original skill taxonomy; not the official objective descriptions |
| [Assessment rubrics](assessment/RUBRICS.md) | Transparent unofficial reading/writing feedback and revision policy |
| [Session log template](assessment/SESSION_LOG.md) | Portable progress summary within a private ChatGPT conversation |
| [Original diagnostic](content/DIAGNOSTIC_01.md) | Reading, analytical writing and self-reflection pilot |
| [Original lesson 1](content/LESSON_01.md) | 50–60-minute reading-to-writing pilot |
| [Four-week study plan](curriculum/PILOT_4_WEEK_PLAN.md) | 20 original, provisional daily session outlines; not a complete official course |
| [Teaching approach](research/TEACHING_APPROACH.md) | EdTech-derived methods and references |
| [Source and capability status](knowledge/STATUS.md) | What the tutor may and may not claim |
| [Agent security rules](AGENTS.md) | Public GitHub scope, privacy and read-only boundaries |

## Intended learning experience

- **Student:** English-language lessons, one question at a time, evidence-based reading, essay drafts and revision, targeted feedback, 50–60-minute sessions on approximately five study days per week (adaptable to travel).
- **Parent:** optional Russian-language study summary prepared by the student, with completed work, skill evidence and next steps. The tutor does not secretly report or publish the student's private conversation.
- **GitHub writes allowed only to public `progress/` statistics when authorized.** Public files can be viewed via their GitHub URLs or downloaded and uploaded as plugin reference files. GitHub `progress/` is the owner-approved lightweight lesson checkpoint store.
- **No automatic sync.** Editing this repository does not automatically update a plugin already created in another account. Ask @plugin-creator to update the plugin, or supply updated files.
- **Automatic checkpoints are required but not yet connected.** ChatGPT may use the current conversation to track progress. A separate authenticated learning app and database are a future project; this public plugin does not have that connection.

## Privacy and licensing

This is a **public** repository. Never commit personal details of a child, student essays, school login details, chat transcripts, Telegram IDs, OpenAI API keys or credentials. The reading passages and exercises here were authored for this project. Cambridge documents and third-party lesson content remain the property of their respective rights holders and are **linked, not copied**.

This repository is **not** the owner's private infrastructure repository. No instructions here authorize changes to other repositories or production systems.
