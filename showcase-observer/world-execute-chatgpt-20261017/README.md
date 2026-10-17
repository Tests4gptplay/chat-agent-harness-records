# External CAH Showcase Observer — world.execute(me)
 
Source task: `world-execute-chatgpt-showcase-20261017`
Source canonical Git: `Tests4gptplay/git-agent-harness`, branch `main`.
This observer's **separate private** record destination: `Tests4gptplay/chat-agent-harness-records`, branch `main`.
 
## Purpose
Retain read-only, externally authored evidence of the real CAH runtime during the full-song music-visualization showcase. Observe hourly, using timestamped append-only files. Verify against Git Task Cell, Planner turn outcomes, Child CL/Reply/Result, Workflow run/job/log, immutable commit refs, and specific real artifacts when necessary. Compare against the previous observation. Include genuine failures and incomplete recovery, not only success.
 
## Non-interference
Never modify source CAH's task, CL, lanes, roles, control requests, dispatches, prompts, Workflows, Runners or project work files as part of the routine hourly observer. Do not wake/stop/restart a Worker or use a control endpoint. Git READ operations are sufficient for routine hourly checks; do not dispatch a short task every hour. The one-time local read-only `cah-shot` probe was performed independently to establish this baseline.
 
## Recording convention
- `baseline.json`: initial observation after one-time host proof.
- `hourly/YYYY-MM-DD/YYYY-MM-DDTHH-mmZ.json`: one observation per UTC hour; use explicit capture time, provenance and last seen commit, and create-only writes. When no meaningful changes, save a very compact no-change heartbeat.
- `events/YYYY-MM-DDTHH-mmZ.json`: optional independent event file for verified state transitions and failures, cited to immutable Git/Actions refs.
- `final-observation.md`: end-of-task factual synopsis with evidence limitations; only after terminal/cleanup is independently observed.
- Never touch the existing cold-archive `INDEX.json` for these observations.
 
## Evidence discipline
`observed` means directly checked canonical Git, Actions or local disk; `inferred` means a cautiously explained interpretation; `unknown` remains unknown. A Runner response-start does not prove local filesystem work; one local command process absence does not prove an Agent is idle. Include updates to Worker generation/fence, Planner completion reductions, runner capacity, failures and recoveries, actual files and hashes. Respect project privacy and exclude personal identifiers/raw audio/binary assets.
 
## Terminal policy
After a verified parent terminal result and Cleaner record export, write a final synopsis and disable the scheduled observer if technically possible; otherwise request a single user action to stop it. Never write a fabricated terminal report to make the schedule end.
