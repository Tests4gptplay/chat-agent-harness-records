# CAH MV External Observer — Gap Reconciliation

**Recorded retroactively:** 2026-10-17 19:19:28 UTC (2026-10-18 04:19:28 JST).  
**Source of truth:** [Tests4gptplay/git-agent-harness](https://github.com/Tests4gptplay/git-agent-harness), **main** only.  
**Task:** `world-execute-chatgpt-showcase-20261017`.  
**Destination:** this separate private records repository; no CAH task, Planner, Worker, Helper, Runner or Action was modified to create these observer records.

## Scope and method

The observer was disabled while the originally scheduled UTC 16:00, 17:00 and 18:00 snapshots were not saved. The original `14:30` baseline/`15:00` observation and the later **real** `19:00` observation were preserved unchanged. Three missing slots are now filled with **`kind=hourly_retrospective_backfill`**. Each uses the exact latest canonical Git commit preceding its named UTC hour, reads historical Task Cell and relevant Child backend state at that commit, and cites immutable Worker Results and dated Windows Actions. `reconstructed_at_utc=19:16:33Z` is the actual later collection timestamp; no model claims that a clock-driven observer ran during the gaps.

| UTC hour (JST) | Capture classification | Source commit as-of cutoff | Key verified frontier |
| --- | --- | --- | --- |
| 14:30 (23:30) | Existing actual baseline | See `baseline.json` | Original director design and workdir |
| 15:00 (00:00) | Existing actual hourly snapshot | `07f89efb9fce2ff8641c4ff164fdd69dad719ba8` | Original audio/cues, deterministic render core |
| **16:00 (01:00)** | **Retrospective backfill** | [`36e7bda5be2f6b63d54e227ba0587c364aef6552`](https://github.com/Tests4gptplay/git-agent-harness/commit/36e7bda5be2f6b63d54e227ba0587c364aef6552) | S01–S10 Worker result complete; Planner review was still pending |
| **17:00 (02:00)** | **Retrospective backfill** | [`4e9790c490d71c10af59d0fdbc466f016444df06`](https://github.com/Tests4gptplay/git-agent-harness/commit/4e9790c490d71c10af59d0fdbc466f016444df06) | S11–S17 accepted, A5 S18–S20 host-verified partial, context Child G2 admitted |
| **18:00 (03:00)** | **Retrospective backfill** | [`70813cd10850dacd6247b96a14e3a71bcc2176c3`](https://github.com/Tests4gptplay/git-agent-harness/commit/70813cd10850dacd6247b96a14e3a71bcc2176c3) | A6 PowerShell launch failures, bounded Helper probe, Planner NEED_USER |
| 19:00 (04:00) | Existing actual hourly observation | `379f4a9c2da4076b62dbdd222ca53b40f6f74f01` | Second Helper's historical temp-file absence, G2 Planner review in progress |
| **19:19 (04:19)** | **Later observer event checkpoint** | [`44b4ff769dbc5a663fa538045a42d2a2c12e5ca8`](https://github.com/Tests4gptplay/git-agent-harness/commit/44b4ff769dbc5a663fa538045a42d2a2c12e5ca8) | Original context Child G5 admitted, guarded workflow source updated; no A6 PASS |

## Immutable files and exact readback

- [16:00 backfill](../hourly/2026-10-17/2026-10-17T16-00Z.json) — blob `19ca92f3f673eb588f4517d8e06b1e48b7169765`.
- [17:00 backfill](../hourly/2026-10-17/2026-10-17T17-00Z.json) — blob `5f37e7012c30ba122ecc77b86ad28526cc1ff39f`.
- [18:00 backfill](../hourly/2026-10-17/2026-10-17T18-00Z.json) — blob `8c70beef0eb9f77bfcff77959a4cade3c8a15cdf`.
- [19:00 original observation](../hourly/2026-10-17/2026-10-17T19-00Z.json) — blob `ecbe41ec3c53a75727380804d9b7ab9b404e6199`; **not overwritten**.
- [13-event historical chronology and 19:19 current checkpoint](../events/2026-10-17T19-19Z.json) — blob `1c6394fbc7aacab1985dcbc97e17e67ce188363a`.

The original 19:00 JSON's `previous_ref` still points to 15:00 because the three missing records did not yet exist when it was captured. This is not silently corrected: the later backfill chain is `15:00 → 16:00 → 17:00 → 18:00`, while the original 19:00 observer document preserves its own original observed genealogy. Follow the event ledger or this reconciliation note to bridge those branches.

## Critical incident and trust boundaries

- Two original A6 Managed host jobs failed at `pwsh -File` *before* A6 builder/visual QA markers: [39052287495](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39052287495) and [39052721378](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39052721378). Neither proves the source artwork failed.
- The user confirmed Huorong interception of generated `gah-managed-*.ps1` and later restored **two specific original instances only** through Task Contract revision 2. This is not a directory-wide whitelist or automatic malware-clearance verdict. [Source issue #392](https://github.com/Tests4gptplay/git-agent-harness/issues/392).
- Helper [39053988919](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39053988919) diagnosed a benign script probe and static source; later Helper [39060400024](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39060400024) found both *historic* temporary script paths absent and failed closed. Planner subsequently inspected the workflow `finally` cleanup: absence after job completion alone cannot be evidence of new quarantine.
- Planner G2 continued the **same context Child** through an explicit safety-gated direction. Worker G5 was acknowledged at 19:16Z; the `.github/workflows/managed-host-script.yml` hash/parser hardening source changed at [c26039fd](https://github.com/Tests4gptplay/git-agent-harness/commit/c26039fd0037ba59ccbfcf3d954d32b78dcb561b) and [44b4ff76](https://github.com/Tests4gptplay/git-agent-harness/commit/44b4ff769dbc5a663fa538045a42d2a2c12e5ca8). **Those commits do not prove that a guarded host run has passed.**

## Observer verdict and next evidence gate

真实收益包括原始设计/音频/字幕时间轴、已验证的 S01–S17 和 A5 S18–S20 动画素材，以及可复核的故障/接续证据。迄今并未验证 A6 S21–S23、新增 18+ 张全高清场景帧、后续 A7/A8、211.906667 秒完整音视频或最终 A1–A8 全部验收。**“RUNNING”只是正式接收 dispatch，不是连续渲染证明。**

下一次独立观察应优先寻找 G5 正常 Managed Runner 的预执行 hash/parser 检验是否实际运行、有无新的火绒告警、14 个保护输入哈希是否实际通过，以及 S21–S23 首批真帧。无真实证据就继续标为未知，不要求 CAH 重新调度，也不因旁观操作启动 Runner。每小时观察保持 create-only，若时段文件已存在则读回并跳过；已有快照与冷归档 `INDEX.json` 永远不覆盖。

**No public publication.** Future public Showcase must sanitize machine paths, personal identity and third-party audio/assets.
