# CAH Record Archive

Cold historical records for Chat Agent Harness (CAH).

Active orchestration state remains in `Tests4gptplay/git-agent-harness`.

`INDEX.json` is the entry point for archived tasks. Normal CAH agents do not read this repository unless history, audit, recovery or user-requested archive work requires it.

Archive data lives under `records/<task_id>/...`. The active CAH repository does not keep per-task archive pointers.
