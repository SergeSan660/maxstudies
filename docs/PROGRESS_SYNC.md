# Automatic progress checkpointing — public GitHub

**Owner decision:** Store **non-personal lesson completion statistics and resume checkpoints** in the **public** `SergeSan660/maxstudies` repository. This decision is intentional. Do not override it with a private-repository requirement. No full essays, conversations, personal identifiers, account details or credentials belong in these progress files.

**Implementation status:** Protocol and file schema specified below. Automatic writes are **not yet connected or tested in the student's ChatGPT account**. The tutoring skill cannot write to GitHub without an authenticated GitHub app or a purpose-built, restricted write integration.

## Files

- [`progress/current.json`](../progress/current.json): authoritative checkpoint for next lesson and most recent completed work.
- [`progress/history.jsonl`](../progress/history.jsonl): append-only per-session **summary statistics**, without essay text or personal information.
- [`progress/README.md`](../progress/README.md): field meanings and limitations.

## Start-of-session algorithm

1. Read `progress/current.json` **from the latest `main` branch commit**, not from stale plugin instructions. If the tool cannot access the repository, say that progress sync is unavailable and ask to reconnect; do not pretend to know the next lesson.
2. Check `schema_version`, `plan_id`, `next_session` and `checkpoint_status`. Validate `next_session` against the [four-week pilot](../curriculum/PILOT_4_WEEK_PLAN.md).
3. If `checkpoint_status` is `in_progress`, resume the saved session and stage; if `ready`, start `next_session`. Never skip a session merely because calendar time passed.
4. Before a new lesson, review the recent compact history to adapt practice to demonstrated gaps and retention due. Avoid reading or displaying any personal identifiers.
5. If the record is missing/corrupt/conflicting, **do not increment** the session. Ask for confirmation and recover from the last valid record.

## End-of-session algorithm

1. Evaluate whether the required lesson tasks were **actually completed**. A partially finished session stays `in_progress` with a stage pointer.
2. Compute minimal statistics: session number, lesson slug, duration if volunteered, number of tasks attempted/completed, rubric categories observed (0–3), help level, retention state, next action.
3. Update `progress/current.json` and append a matching event to `progress/history.jsonl` through an **authenticated GitHub write tool** restricted to the `SergeSan660/maxstudies` repository. Never attempt writes in any other repository.
4. Read back both files after writing and verify that the `event_id`, session pointer and expected counts match. Only then say **“Progress saved. Next lesson: ...”**.
5. If a write fails, say **“Progress was not saved to GitHub.”** Retain a small recovery record in the current chat and retry only when permitted. Never advance a checkpoint based solely on a model-generated claim.
6. Avoid duplicate events: use a stable `event_id` for retries, verify no existing matching event, and update using GitHub file SHA to detect concurrent changes. If a conflict occurs, re-read, reconcile and retry once; otherwise ask for help.

**Important GitHub limitation:** The repository's GitHub integration must have actual permission to read/write files; this is **not** created by adding text to a prompt. If the student account cannot connect GitHub or the plugin cannot invoke write actions, use a separate restricted progress API or report the blocker. Do not claim automation is active.

## Data minimisation

Allowed: numeric lesson indices, content slug, counts, objective **codes**, numeric formative scores, help-level categories, duration bucket, status and next-stage pointer. Use a generic dataset key `cambridge-english-stage9-pilot`, not a student name or GitHub username.

Disallowed: full name, date of birth, location, email, Telegram IDs, school login, IP, personal biography, essay/draft text, quotations from a student's answer, raw AI chat transcripts, free-form notes that could reveal private information, API tokens or access credentials.

Even anonymous-looking progress can be linkable to the public repository owner; keep the dataset minimal as requested.

## Session progression rules

- `next_session` begins at 1 and advances only after the previous lesson is actually completed and the GitHub save is verified.
- A pause, travel day or missed date does not advance the lesson counter.
- Completion and mastery are separate: a completed lesson may leave skills requiring practice.
- The four-week plan contains sessions 1–20; after session 20, set `next_session` to `null` and `checkpoint_status` to `plan_complete`. Do not invent a session 21.
- A new lesson plan requires an explicitly added plan version, not a guess.

## Tool-access gate

To enable real automatic writes, the student must have an **authorized** GitHub integration capable of `fetch_file` and `update_file` or an equivalent approved repository-scoped tool. Configure permissions for **only** `SergeSan660/maxstudies` and **only** the required content paths if supported. Do not give the agent unrestricted access to the parent's other repositories. If GitHub integration is unavailable to the student's account or plugin, the owner/operator must supply a restricted alternative; this file alone cannot activate it.
