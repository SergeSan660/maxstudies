# Public progress — Cambridge Stage 9 pilot

The project owner has explicitly chosen to store **minimal, non-personal lesson statistics** publicly in this repository.

- `current.json`: current checkpoint; start here at every session.
- `history.jsonl`: one compact statistical event per completed/paused session.

This directory intentionally contains **no** student identifiers, essays, chats, passwords, Telegram IDs, school records or personal narratives.

The files are **initialized but not automatically updated**. For automation, the student's ChatGPT plugin needs an authenticated GitHub write-capable integration restricted to this repository, or an operator-provided restricted progress API.

**Fields in `current.json`:** `schema_version`, `plan_id`, `checkpoint_status`, `next_session`, `current_stage`, `last_completed_session`, `last_event_id`, `skills_to_review`, `updated_at`. `updated_at` is null until a real write.

**History event fields:** `event_id`, `session_number`, `lesson_slug`, `status`, `tasks_attempted`, `tasks_completed`, `rubric_scores`, `help_level`, `retention_state`, `next_session`, `timestamp`.

Avoid free-text notes. Each rubric score is formative, unofficial, and is not a Cambridge mark.
