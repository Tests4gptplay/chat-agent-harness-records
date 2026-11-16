# CAH retrospective continuity episodes

Maintainer-authorized, privacy-sanitized evidence extract, prepared 17 November 2026. This report records engineering observations; it does not publish media assets or the research manuscript.

## Scope and selection

The evidence covers two engineering workloads: A, the September Viewer/Cook task already documented publicly; and B, an October multi-day media-build campaign. B1–B4 below are correlated episodes of that same campaign. C1 is a separate infrastructure incident, not another completed engineering task. Selection is purposive: the episodes distinguish task continuity, physical recovery, user-directed revision, terminal archival and unavailable recovery resources. Both completed and unresolved outcomes are retained. This is not an exhaustive incident census or a sample for estimating autonomous success probability.

Original repository records were read at fixed revisions. Helper and Planner reports remain attributed to those roles. Two historical Windows job logs additionally corroborate the post-repair closure. The source identifiers below resolve through an owner-retained provenance map; original private logs and artifacts remain private. Short excerpts reproduce actual output lines, not echoed test scripts. These historical jobs were not rerun for this report.

## A1 — Viewer/Cook field chronology

The 28 September task accepted its first phase after 5 h 01 m 30 s and a provenance investigation after 7 h 21 m 28 s. It reached a durable G31 handoff at 17 h 47 m 56 s after two human recovery interventions. A later G32 conversation stopped without usable output. This is the existing developmental case, not a newly added successful task.

Public source S01: [frozen chronology](https://github.com/Tests4gptplay/chat-agent-harness/blob/d9c5453df87c0fd261f8ffbb90df3d8727525797/showcases/ue-parallel-viewer/records/2026-09-28-rerun-record.md).

## B1 — Restart followed by continuation of the same task

The observer record combines a user-reported Windows restart with timestamped post-restart Git observations. The last verified pre-restart task state was WAIT_USER. On 18 October (UTC), a health report at 00:24:29 was followed by detection of the original parent's changed intent at 00:24:34, Planner staging at 00:25:18 and prompt delivery at 00:25:56. These differences are 5, 49 and 87 seconds from the recorded health checkpoint, not OS boot latency. Later work continued the same logical Child; actual image QA still found defects.

Public source S02: [frozen observer event](https://github.com/Tests4gptplay/chat-agent-harness-records/blob/6c4bf282127aeeb0713509ad1622e8acc93d3644/showcase-observer/world-execute-chatgpt-20261017/events/2026-10-18T01-33Z.json). The evidence establishes task-state continuation from a waiting checkpoint, not recovery of an interrupted computation or electrical power-loss consistency.

## B2 — Physical retry and a later user-directed branch stop

A primary Helper report records an incomplete tool call with no usable result, replacement of the exact physical conversation, and a new response-start at 08:36:26 UTC on 19 October. Task, dispatch, generation, fence, wake and Worker ownership were preserved. The report also records correction of an obsolete wait for manual regeneration of the deleted conversation.

A later primary report records a different decision: the user stopped the old branch. The Child changed to CANCELLED, its result reference stayed null, and the parent task and Planner direction survived. The observer backfill records cancellation consumption at 09:43:39, Helper-result consumption at 09:48:45 and a replacement planning route. An unsuitable generated image was rejected; restoration was not treated as artistic acceptance.

S04 primary recovery blob: `324d34e57a4c51ac59610d4118fab47d9974966b`.

S05 primary user-stop blob: `715a5ebbadb1fa929cafc15ac4d2d4d44fcb8345`.

Public corroborating source S03: [frozen retrospective backfill](https://github.com/Tests4gptplay/chat-agent-harness-records/blob/6c4bf282127aeeb0713509ad1622e8acc93d3644/showcase-observer/world-execute-chatgpt-20261017/backfills/2026-10-19T10-05Z-helper-image-replanning.md). It is a backfill with acknowledged observation gaps, not continuous live monitoring.

## B3 — Qualified outcome acceptance before retirement

The Planner's 22 October (JST) final record accepted a private first draft with qualifications. Recorded technical properties were 211.900 seconds, 6,357 frames, H.264 at 960×540 and 30 fps. The acceptance record retained its quality qualifications and expressly left archive creation, terminal cleanup and user-facing presentation to subsequent responsibilities. These properties are extracted from the historical acceptance record, not newly measured media.

S06 acceptance-record blob: `2b1b51fd49707ac86609bf5c1c7ff3787f2f1fbf`. Original media, music, lyrics, images, project titles, paths and artifact hashes are excluded from this extract.

## B4 — Archive closure and reconstruction of physical Host state

The maintenance issue recorded all 11 owned conversation-deletion receipts complete while task closure remained CLEANING/CLAIMED. Its follow-up attributed a remaining archive failure to Windows command-line length when staging 781-plus paths, alongside serial object-read costs. A subsequent deployed repair and a separate physical-state reconstruction were operator-assisted maintenance, not autonomous Helper-only recovery.

The recovery log checked empty task and Worker project lists, backed up a 202,113-byte zero-filled physical-state file, reconstructed disposable bindings, and observed canonical DONE/IDLE. The archive readback was 14,517,446 bytes. A separate idle observation reported 27 samples, zero new task-cell tabs, unchanged Git configuration and persistent DONE/IDLE. The observation loop was configured for 135 seconds. Its start marker to sample summary spans about 135.389 seconds.

S08 selected recovery output, UTC (verbatim lines):

```text
2026-10-26T15:28:10.3240062Z CAH_RECOVERY_PROJECT={"id": "task-cell", "first": 0, "second": 0}
2026-10-26T15:28:14.5958076Z CAH_RECOVERY_PROJECT={"id": "lane-00", "first": 0, "second": 0}
2026-10-26T15:28:18.7962445Z CAH_RECOVERY_PROJECT={"id": "lane-01", "first": 0, "second": 0}
2026-10-26T15:28:48.4058384Z CAH_TASK_STATUS phase=IDLE cell=DONE active=
2026-10-26T15:28:48.4707932Z CAH_RECORDS_FILE_EXISTS=True
2026-10-26T15:28:48.4747200Z CAH_RECORDS_FILE_BYTES=14517446
2026-10-26T15:28:48.4755655Z CAH_ORIGINAL_TASK_DONE_IDLE_PASS
```

S09 selected idle-check output, UTC (verbatim lines):

```text
2026-10-26T15:30:14.3764170Z CAH_IDLE_OBSERVATION_START
2026-10-26T15:32:29.7650999Z CAH_IDLE_SAMPLES=27 TASK_CELL_BASELINE=0 MAX=0 NEW_IDS=0
2026-10-26T15:32:29.7662998Z CAH_GIT_CONFIG_HASH_UNCHANGED=True
2026-10-26T15:32:29.7840632Z CAH_IDLE_HOST_ROLE_BINDINGS=0
2026-10-26T15:32:29.7869824Z CAH_IDLE_HARNESS_ERROR_ACTIVE=False
2026-10-26T15:32:31.5458491Z CAH_IDLE_CANONICAL phase=IDLE taskcell=DONE
2026-10-26T15:32:31.5470613Z CAH_ISSUE409_IDLE_STABILITY_PASS
```

The issue's closure report distinguishes this completed archival/idle recovery from foreground notification: notification remained CLAIMED because the foreground target was unbound. Thus task completion, archive completion, physical cleanup and user-facing delivery were four different facts. S07 is the issue and its two follow-ups; S08/S09 are separate executed Windows logs, not independent external evaluations.

## C1 — Recovery executor unavailable

A 29 October incident record reports a Git snapshot fetch exceeding its existing 20-second bound. Three diagnostic routes were queued without an assigned Runner at that record's last check. Canonical state was IDLE, but no live Host probe or verified repair occurred; the report omitted the done signal. This is an unresolved historical checkpoint, not a claim about current Runner availability.

S10 incident-record blob: `1b6321a487d3babfd909ef4e35326831b7af5ecb`.

## Reusable observations

The records distinguish preserved task identity from a healthy executor, physical retry from user-directed task revision, outcome acceptance from archival/cleanup, and completed cleanup from delivered notification. The unavailable-runner incident also shows why readable durable state alone cannot ensure progress. Qualified results, failed QA and human intervention remain part of those observations.

The October dates describe a campaign and later maintenance, not ten days of uninterrupted autonomous uptime. No historical incident counts are combined with laboratory crash trials.

## Privacy and provenance

Only selected operational facts and output lines are released. Account and conversation identifiers, host names, credentials, local paths, original media and unrelated conversations are excluded. Source blob identifiers are original-byte provenance identifiers; they are not checksums of the rewritten extracts. A private source map is retained by the owner. Existing records are unchanged.
