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
- `final-observation.md`: end-of-task factual synopsis, independent evaluation, and evidence limitations; only after terminal/cleanup is independently observed.
- Never touch the existing cold-archive `INDEX.json` for these observations.
 
## Evidence discipline
`observed` means directly checked canonical Git, Actions or local disk; `inferred` means a cautiously explained interpretation; `unknown` remains unknown. A Runner response-start does not prove local filesystem work; one local command process absence does not prove an Agent is idle. Include updates to Worker generation/fence, Planner completion reductions, runner capacity, failures and recoveries, actual files and hashes. Respect project privacy and exclude personal identifiers/raw audio/binary assets.
 
## Independent observer commentary (every hourly snapshot)
Every `hourly/*.json` snapshot must also contain an `observer_commentary` object, written in **Chinese**, separate from the machine-fact/observed-event fields. The commentary is the outside observer's interpretation, **not** a CAH instruction, completion signal, an Agent self-report, or an unverified truth. Use this compact structure:

```json
{
  "observer_commentary": {
    "assessment": "独立价值判断：本轮有无实质进展，以及失败是否真正提供新信息",
    "architecture": "架构观察：规划、分工、接续、Recovery、工具路径的实际表现",
    "watch_next": "下轮最值得核查的一个尚未验证的问题",
    "confidence": "high|medium|low",
    "evidence_refs": ["exact immutable Git commit, result file, or GitHub Actions URL"],
    "uncertainties": ["what remains unobserved or unverified"]
  }
}
```

For runs with meaningful changes, keep commentary around **100–200 Chinese characters total** across assessment, architecture, and watch_next (shorter is fine if evidence is sparse). For a no-change heartbeat, keep **one or two short factual sentences**, without padding or recycled praise. The `evidence_refs` array may be empty only when there is genuinely no new trustworthy source.

Evaluate a failed attempt by **information gained, usable checkpoints, repetition avoided, and continued task progress**, not by raw success/failure counts. Three failed script attempts can expose an actionable wrapper defect, but repeated equivalent no-progress attempts should be called out. Distinguish ordinary G1→G2 `continue` from tested watchdog/Helper fault recovery. Do not infer continuous productive work merely from `RUNNING`, lack of new commits, or process snapshots. Express uncertainty frankly and allow negative assessments where warranted.

The Observer has no semantic or operational authority over CAH. Comment only in its separate private record: **never** give Worker/Planner instructions, alter the source repository, create GH Issues, reroute work, awaken Agents, or change the production workspace. Only notify the user for meaningful faults requiring attention, user decisions, or independently verified terminal delivery; commentary alone is not a notification trigger. Preserve all historical snapshots unchanged, including any initial baseline predating this rule.

## Terminal policy
After a verified parent terminal result and Cleaner record export, write a final synopsis and disable the scheduled observer if technically possible; otherwise request a single user action to stop it. Never write a fabricated terminal report to make the schedule end.
