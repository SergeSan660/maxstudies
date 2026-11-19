# Set up Aishka in your own ChatGPT account

Aishka is a private study coach for Cambridge Lower Secondary English Stage 9. She helps you **think, read, write and revise**. She won't write your assignments for you.

## Option A — create a private plugin

1. Sign in to **your own** ChatGPT account. If your account has teen settings, keep the parental controls and permissions your family has agreed on.
2. Open **Plugins** in ChatGPT. Look for **Plugin Creator** and install it if your account offers it.
3. Start a chat with **@plugin-creator**.
4. Open [PLUGIN_CREATOR_PROMPT.md](../PLUGIN_CREATOR_PROMPT.md), copy the section beginning **“Create a private plugin called Aishka…”**, and paste it into the Plugin Creator chat.
5. Ask the creator to build a **private skill-only plugin**. **Do not connect a GitHub app**, enter a password, or give it permission to edit repositories.
6. If Plugin Creator cannot open the public files, download/upload these exact files from this repository: [SKILL.md](../skills/aishka-tutor/SKILL.md), [STATUS.md](../knowledge/STATUS.md), [RUBRICS.md](../assessment/RUBRICS.md), [DIAGNOSTIC_01.md](../content/DIAGNOSTIC_01.md), [LESSON_01.md](../content/LESSON_01.md), and [curriculum guide](../curriculum/README.md). It may also need the [objective index](../curriculum/STAGE9_OBJECTIVES.csv).
7. Once created, test it with: **“@Aishka Start my Stage 9 English diagnostic. Ask one question at a time.”**

If the **Plugins** or **Plugin Creator** option is unavailable, do not try to bypass your account's settings. Use Option B instead.

## Option B — use a normal private ChatGPT chat

Open a new private ChatGPT conversation. Attach the four files **SKILL.md**, **STATUS.md**, **RUBRICS.md**, and **DIAGNOSTIC_01.md** (or paste their contents). Then write:

> Act as Aishka, my Cambridge Stage 9 English tutor. Follow the attached instructions. Start my diagnostic, one question at a time. Do not write my answers for me.

This gives you the same **study workflow** without installing a plugin.

## Your first week

- **First session:** complete the [original diagnostic](../content/DIAGNOSTIC_01.md). You should do the thinking and writing yourself.
- **Next session:** start [Lesson 1 — The Museum of Unsent Letters](../content/LESSON_01.md).
- **Follow-up lessons:** use the [four-week pilot plan](../curriculum/PILOT_4_WEEK_PLAN.md) to choose the next task.
- **After each session:** ask **“Give me a session record and one skill to practise next.”**
- **If you are travelling:** say **“I have 15 minutes today. Give me a short practice session.”**
- **When you want to improve an essay:** say **“Let's work on my first draft. Give feedback on one rubric category at a time.”**

## What Aishka can and cannot do

**Can:** discuss original passages, ask questions, give hints, assess with an unofficial rubric, help you revise and summarize the current chat.

**Cannot yet:** know your school's private assignments, automatically store progress in a database, send you Telegram reminders, fetch your past chats reliably, certify Cambridge grades or read private GitHub repos.

The public GitHub repository is a **library of study instructions**, not your school account or a place to submit work. **Never post your real name, address, passwords or essays in GitHub issues.** Keep your answers in your private ChatGPT chat.

If a plugin is already created and the GitHub files later change, ask **@plugin-creator** to update it. GitHub changes are **not** automatically synchronized.
