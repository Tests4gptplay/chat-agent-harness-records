# CAH legacy branch audit — 2026-10-18

**Independent Cache Study archive is complete and hash-verified:** [temp archive](https://github.com/Tests4gptplay/temp/tree/main/work/cache-study) (commit `a39fc10`). Exactly 45/45 research/workflow blobs preserved byte-for-byte; no activated workflow copied.

## Branch findings

- CAH has **74 branch refs** at this audit, including `main`.
- **1** clearly misplaced independent Cache Study branch: `research/latent-kv-transfer-r1-20261018`; its 45 additions were isolated from `main`, migrated and verified.
- **25** old branch heads proved to be ancestors of `main` in Git comparisons (`ahead_by=0`). They can be pruned without losing commits, provided they are still merged at the deletion instant and have no open PR or active dependency.
- **3** open PR branch heads retained: `#349 fix/348-planner-turn-ceiling`, `#330 fix/329-conversation-load-retry`, `#149 fix/148-cleaner-lane-residue`.
- **47** other branch refs retain distinct history or release/task provenance; keep pending case-by-case review rather than deleting CAH-owned work arbitrarily.

## Safe cleanup plan
1. Preserve every ref SHA in `CAH_BRANCH_INVENTORY_20261018.json`.
2. For each merged candidate, require the ref's current SHA equals the inventoried value, branch is not protected, `compare/main...branch` gives `ahead_by==0`, and no open PR points to the branch.
3. Remove confirmed merged refs with GitHub API; skip any changed branch.
4. Delete the migrated Cache Study branch last, checking its archive exists and branch head has not diverged.
5. **Never modify CAH `main` or self-hosted Runner.**

Only the research branch is confirmed to be unrelated study pollution. A stale fully merged development branch is Git hygiene, not evidence of unrelated research pollution. Divergent branches may hold useful work and are not automatically classed as garbage.

## Post-cleanup verification — 2026-10-18

**Observed after interrupted cleanup resumed (authoritative refs queried live):**

- Starting CAH branch inventory: **74 refs including main**.
- Remaining CAH branches: **48 refs including main**.
- **26 refs absent** versus the pinned inventory: **25 exactly matched previously verified fully-merged (`ahead_by=0`) candidates** and **one external-research branch** `research/latent-kv-transfer-r1-20261018`.
- All removed names were present on the inventory's explicit safe-delete candidate lists; **no extra or unplanned branch deletion was detected**.
- All three open PR head branches survived: `fix/348-planner-turn-ceiling` (#349), `fix/329-conversation-load-retry` (#330), `fix/148-cleaner-lane-residue` (#149).
- The other **47** surviving references besides `main` have reasons to preserve (divergent changes, release/task provenance, open PR). **Their usefulness was not individually certified**, and they were not mass-deleted.
- CAH `main` checked: **zero files** under `research/latent-state-transfer/` or `work/cache-study/`, and **zero** `.github/workflows/research-*` entries. Live CAH main moved naturally while the audit ran; this cleanup did not require force-updating main.
- The 45 archived source blobs under `work/cache-study/` match the original pinned source Git blob SHA-1 and file byte lengths, with **0 mismatches**. Exactly eight former GitHub research workflows are preserved under `archived-workflows/` as nonexecuting fixtures.
- Archived source commit: `77f495481094fc7c3085f83d9f3537510655c804`. Complete migration commit: `a39fc10d26f27cd12650fb678ac11220cda151b7`.
- Final verification should not be confused with identifying who/what triggered the remote ref deletion; that actor is not established by the accessible GitHub refs. The result was independently verified after the interruption.

**Conclusion:** Independent Cache Study files were evacuated into temp; the offending CAH branch was removed; stale fully-merged branch refs were pruned. Other divergent CAH branches are preserved until a separate per-branch review confirms they are unnecessary.

---

## 2026-10-18 Phase 2: all 47 remaining non-main branches

Pinned CAH main at phase-2 read: `4a04e9d76257afac34893f7b7834b44c9b4aeae4`. Original 48 refs total (47 + main). This is an immutable SHA inventory, not proof of later deletion. No CAH active main files are changed by this report. GitHub PR head SHA comparison and open PR list are used as a stronger criterion than mere ahead/behind divergence. All 47 branches diverged from main by commit graph; merge via squash/cherry-pick can leave an ahead count even after integration.

**Disposition before execution:** {"PRUNE_MERGED_PR_HEAD":32,"HOLD_UNMERGED_NO_PR":11,"HOLD_POST_MERGE_DIVERGENCE":1,"HOLD_OPEN_PR":3}.

### 32 exact merged-PR head refs eligible for guarded deletion

| Branch | Pinned HEAD SHA | Basis |
|---|---|---|
| `case/301-ankleswap-winding-prevention` | `2987417ab39d0afd995f203c18d350cb171e78e2` | PR #302 merged 2026-09-27 |
| `cleanup/retire-task-payloads-283` | `83995a39e2d0e3d9fded3b1ff4fcb9464dfd128f` | PR #284 merged 2026-09-27 |
| `cleanup/371-purge-stale-hot-cache` | `5c25e48a938c38c791891bb81ef55870c4cf46cf` | PR #372 merged 2026-09-29 |
| `docs/main-installation` | `d5f824a567932ec9915f669a5f18ad30dcb148cc` | PR #267 merged 2026-09-26 |
| `docs/planner-execution-checkpoints` | `38f72f513a407943a7f138cf924f884ff0ff6a6d` | PR #276 merged 2026-09-27 |
| `docs/shared-external-authorization` | `4e31da522508c47338486385c7b8f7c3f5c537a2` | PR #278 merged 2026-09-27 |
| `docs/three-tier-installation-boundary` | `751764d00cbdb56f44027554ea390f35fc665b6a` | PR #279 merged 2026-09-27 |
| `docs/worker-iteration-planner-review` | `52d36b3fe41cb40ddf049a0b6aebc40662546f10` | PR #277 merged 2026-09-27 |
| `docs/312-short-task-memory` | `92326f69e7ab9626a6838a01957f919c5e160b4d` | PR #313 merged 2026-09-27 |
| `docs/314-foreground-entry-routing` | `e0074b5f901834c91dd7c59d33cfafa1b1514c77` | PR #315 merged 2026-09-27 |
| `docs/333-planner-governance-observation` | `230dcaaa3d783397ff17709643f5f4b6155cc264` | PR #356 merged 2026-09-28 |
| `docs/333-showcase-provisional-conclusion` | `c286c09a9688a6bf21207056ee757d662acbaa7b` | PR #354 merged 2026-09-28 |
| `docs/333-showcase-timeline-p2a` | `00bb18110936ccb9d5ca9b58eae0afa34f060a21` | PR #355 merged 2026-09-28 |
| `docs/359-runner-watchdog-helper-continuity` | `449f5517764bfb1ae2252645aef57bc045b0916f` | PR #360 merged 2026-09-28 |
| `feat/271-playwright-mcp` | `20602c94c98d2c026467d1996b5f4b84d96131c3` | PR #272 merged 2026-09-26 |
| `feat/318-local-rollover-fastpath` | `d0d2cc1b00b766a448343372917f1d095fc5e9f4` | PR #320 merged 2026-09-27 |
| `fix/recovery-predecessor-binding` | `aac897a2e4d5e16eeac6398982dadf34a14cfbcc` | PR #280 merged 2026-09-27 |
| `fix/worker-liveness-286` | `bed1c2b9fd0c18c8e908b98cda83db91dfde5158` | PR #287 merged 2026-09-27 |
| `fix/worker-liveness-helper-366` | `514661b07e0e79d854d354b8d62cfee53fdc9167` | PR #367 merged 2026-09-28 |
| `fix/worker-planner-watchdog-helper-366-clean` | `fc7d6a545ce5dbe7dd4360a13871c0b6135b28a7` | PR #375 merged 2026-09-29 |
| `fix/271-retired-browser-entrypoints` | `301dd5efb7903ff0cb0a69516bee5959fb741c49` | PR #273 merged 2026-09-26 |
| `fix/297-inline-ankleswap-case` | `ce4216366a72c183f3b786e30ae7b6561504f023` | PR #303 merged 2026-09-27 |
| `fix/299-plan-note-lifecycle` | `8959c5dc36589e719205dd68a8c51d3af4dc15af` | PR #300 merged 2026-09-27 |
| `fix/304-planner-plan-note-semantics` | `77826aeb115e6b1133334fb8af2829f9acdfd2d0` | PR #305 merged 2026-09-27 |
| `fix/306-plan-note-load-shedding-purpose` | `bb5cd03812a2b5a359e8c3bcc26af57417ec0279` | PR #307 merged 2026-09-27 |
| `fix/308-worker-5min-budget` | `8fe7633da7547e12bfbd97fb3fa51e621524fc3c` | PR #309 merged 2026-09-27 |
| `fix/310-helper-runtime-8min-timeout` | `a305be313aad4d873948306dbaab0820915076df` | PR #311 merged 2026-09-27 |
| `fix/346-fresh-worker-per-child` | `e8a87066f59b36fae834e229b8621af758c1c405` | PR #347 merged 2026-09-28 |
| `revert/280-recovery-predecessor` | `d4bcd04a7a7ee75cce47aa61add4fe6cbea18165` | PR #281 merged 2026-09-27 |
| `skill/297-nte-normal-tangent-winding` | `036b0b1aacc6541cced38313be7ea9f64360ea03` | PR #298 merged 2026-09-27 |
| `skill/350-powershell-managed-script-reliability` | `b2f1c5e46b74b787a854927e7dad926193654d15` | PR #351 merged 2026-09-28 |
| `skill/352-powershell-syntax-hygiene` | `ff9cb8c594466108e22b12546e21aebd74b02335` | PR #353 merged 2026-09-28 |

### 3 open-PR heads — keep

| Branch | Pinned HEAD SHA | Basis |
|---|---|---|
| `fix/148-cleaner-lane-residue` | `23f88a942bca7bdd2ae1d4f8cb08b3325f43b379` | PR #149 open |
| `fix/329-conversation-load-retry` | `0407a0286dc803bae07fc3ea11822e6dda69b6f3` | PR #330 open |
| `fix/348-planner-turn-ceiling` | `fb27dc33d6e134b6b94113fe1a3894d86c74b969` | PR #349 open |

### 1 post-merge-diverged head — keep

| Branch | Pinned HEAD SHA | Basis |
|---|---|---|
| `fix/worker-watchdog-helper-366` | `2b42150d16761ecab1af1066ebf772a1954c5d6d` | PR #368 merged; PR head 715c23851803 differs; 122 post-merge commits |

### 11 orphan/release/showcase refs — keep pending semantic review

| Branch | Pinned HEAD SHA | Basis |
|---|---|---|
| `docs/draco-cn14-three-way-case-384` | `199147df9e6da4c451b32f99a31eeacd9dd3d23a` | Issue #384 open; task outcome/Skill evidence |
| `feat/324-headless-cah-browser` | `61811453f478bb1a4623855126a1ea0167dfd883` | Unmerged headless startup alternative; needs semantic discard review |
| `fix/317-remove-premature-run-record-links` | `357dd7c7a3a56ba9eb7babfa43691c7667ee313c` | Unmerged showcase link edit; main still differs |
| `fix/327-worker-lease-helper-recovery` | `1bba29aab4d6b99b586e36329dd319c793fd5625` | Issue #327 open; 11 unmerged commits |
| `ops/cancel-stuck-reset-runs-20260927` | `db8b24295439b7a7ae88c8cf79b2a3cd0e61c100` | One-off cancel of completed run 36308618828; likely obsolete |
| `release/public-1.0.4-verified` | `885a87f7a73e338b0156d5ffe5fd0d212e4a37e4` | Legacy release snapshot; no corresponding tag or merged PR |
| `release/public-1.0.4` | `886fed8d862e995671324a7d4e48ca7b966dfedb` | Legacy public release snapshot; no corresponding tag or merged PR |
| `release/public-104-review` | `18ccc30e0f533f71d3008f8e23aebe3af39ed105` | Legacy release review workflow |
| `showcase/viewer-v18-preview-001-cooked-exec` | `33eb996f6c155b51fda579ba5e35e6a537103712` | Viewer v18 execution/evidence line (131 unique commits) |
| `work/viewer-v18-preview-001-cooked` | `249995d4cda19382ba1e27c5333396b5046607fc` | Viewer v18 cooked line (127 unique commits) |
| `work/viewer-v18-preview-001-native` | `41d1a735405133f2a186bea769eed15455c5fa90` | Viewer v18 native line (119 unique commits) |


Cleanup gates: each ref still at pinned SHA, merged PR matches the branch head, no open PR claims the ref, and only named heads are deleted. Report successful/failed deletions separately; do not assume execution on workflow trigger. Restore possible from the pinned SHA if commits remain accessible. No branch deletion is authorized for held refs in this phase.


---

## 2026-10-18 Phase 2 execute verification

- Remote audit source (historically pinned): [temp audit commit](https://github.com/Tests4gptplay/temp/commit/12eaf22387d3658db7c9f9bdf6a0157f8eed7aa5), later may move when the user consolidates independent research into MMCA.
- [Exact-merge-head cleanup run 39094286795](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39094286795): `completed/success`, 2026-10-18T03:38:41Z.
- Re-read CAH refs: **16 total (main + 15)**. Exactly 32 previously audited merged-PR heads no longer appear. 3 open PR heads #149 #330 #349 preserved.
- No Cache Study/Micro-Model research changes made in CAH; no release/Viewer source branch deleted by that run.

## Phase 3 candidate review, prior to deletion

These are not automatically equal to "merged". Each delete requires pinned ref, no open PR and evidence-specific preconditions. Decision basis from live GitHub Issue contents, main file reads, branch SHA ancestry and public release presence.

| 分支 | 固定 SHA | 原因 |
|---|---|---|
| `feat/324-headless-cah-browser` | `61811453f478bb1a4623855126a1ea0167dfd883` | Issue #324 says headless is not yet supported; 6-line experimental startup path was never merged |
| `fix/317-remove-premature-run-record-links` | `357dd7c7a3a56ba9eb7babfa43691c7667ee313c` | Main now contains the run record linked by its README; old patch would remove a valid link |
| `fix/worker-watchdog-helper-366` | `2b42150d16761ecab1af1066ebf772a1954c5d6d` | Issue #366 explicitly superseded this branch in favor of merged PR #375 |
| `ops/cancel-stuck-reset-runs-20260927` | `db8b24295439b7a7ae88c8cf79b2a3cd0e61c100` | Only cancels one historical run 36308618828, now completed/cancelled |
| `release/public-104-review` | `18ccc30e0f533f71d3008f8e23aebe3af39ed105` | One-shot readback workflow for historical v1.0.4; public v1.0.4 release/tag exists |
| `work/viewer-v18-preview-001-cooked` | `249995d4cda19382ba1e27c5333396b5046607fc` | Strict ancestor of showcase/viewer-v18-preview-001-cooked-exec (behind 0, later head ahead 4) |

### Non-deletable refs at this stage

| 分支 | 固定 SHA | 原因 |
|---|---|---|
| `fix/148-cleaner-lane-residue` | `23f88a942bca7bdd2ae1d4f8cb08b3325f43b379` | Open PR #149 |
| `fix/329-conversation-load-retry` | `0407a0286dc803bae07fc3ea11822e6dda69b6f3` | Open PR #330 |
| `fix/348-planner-turn-ceiling` | `fb27dc33d6e134b6b94113fe1a3894d86c74b969` | Open PR #349 |
| `docs/draco-cn14-three-way-case-384` | `199147df9e6da4c451b32f99a31eeacd9dd3d23a` | Issue #384 open; distinct verified migration + Skill evidence |
| `fix/327-worker-lease-helper-recovery` | `1bba29aab4d6b99b586e36329dd319c793fd5625` | Issue #327 open; 11 distinct commits in Worker recovery path |
| `release/public-1.0.4` | `886fed8d862e995671324a7d4e48ca7b966dfedb` | Independent public release staging history |
| `release/public-1.0.4-verified` | `885a87f7a73e338b0156d5ffe5fd0d212e4a37e4` | Distinct verification/export history; public v1.0.4 release exists |
| `showcase/viewer-v18-preview-001-cooked-exec` | `33eb996f6c155b51fda579ba5e35e6a537103712` | Cooked execution/evidence line with 131 unique commits vs main |
| `work/viewer-v18-preview-001-native` | `41d1a735405133f2a186bea769eed15455c5fa90` | Native Viewer workline diverged from cooked; 119 unique commits vs main |

Do not create a temporary cleanup branch, and do not touch CAH task state or any independent MMCA directories. Execute via CAH's standing `cah-shot` short-task slot, verify actual GitHub refs again after execution and record outcomes here. This audit preserves HEAD SHAs for recovery if Git objects remain accessible.


## Phase 3 execution verified — 2026-10-18

- [Actions run 39094885833](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39094885833): status `completed`, conclusion **success**, update `2026-10-18T03:48:32Z`.
- Live readback: **10 refs** in CAH, `main` plus exactly nine preserved branch refs listed above. All six Phase 3 candidates absent, and no unplanned ref disappearance observed.
- Active CAH task (read-only check after cleanup): `world-execute-chatgpt-showcase-20261017`, phase `RUNNING`. Phase 3 changed no task state file; only the normal mutable `.github/workflows/foreground-direct-command.yml` slot was updated on CAH main to invoke `cah-shot`.
- In total since the 74-ref inventory: 25 fully merged old heads + one misplaced Cache research head + 32 merged-PR heads + six semantically obsolete heads = **64 branch deletions**, leaving **10** total refs.
- The historical release lines are independently divergent; Viewer native vs Cooked-exec lines diverge; do not delete either pair until their unique code and evidence is archived or merged appropriately.
- The three surviving open PRs require fresh base-state engineering review before merge or closure. In particular #149 contains an old `extension/lane_clear_runtime.js` path absent on modern main; do not merge it unchanged. #330 introduces browser Retry handling not found in the current `playwright_host/ui.py`; #349 targets semantic-turn ceiling while current main has a separate `prompt_ceiling` implementation. These PRs were intentionally not closed, merged or deleted.
- This audit was written in `Tests4gptplay/chat-agent-harness-records`, not to the MMCA research tree. There were no writes to either `temp/work/cache-study` or `temp/work/micro-model-composite-architecture-20261016` during Phase 3.


## Phase 4: Conservative value-based review — 2026-10-18

User direction: **do not delete release/history branches merely to reduce branch count**. Preserve any branch with independent reproducibility, code, evidence or rollback value; delete only clearly obsolete references. Viewer task was reported completed by the user, but that fact does not make distinct unmerged Viewer source/evidence automatically disposable.

### Actual deletion: obsolete PR #149

- [PR #149](https://github.com/Tests4gptplay/git-agent-harness/pull/149) closed **unmerged** after documenting why its implementation is superseded. Old changes target `extension/lane_clear_runtime.js`, a retired Chrome Extension file not present on current main.
- Current Playwright Host `playwright_host/runtime.py::_clean_task_conversations` enumerates exact task-and-epoch-owned conversation targets, persists per-target deletion receipts, then on accepted cleanup invokes `HostState.clear_task_roles` and `HostState.remove_lineage` for the exact task and each lane; `playwright_host/state.py` owns task-scoped `task_pools`. The old Extension-era patch should not be merged into the modern architecture.
- [Issue #148](https://github.com/Tests4gptplay/git-agent-harness/issues/148) is deliberately still **OPEN**, since the old PR closure is not a substitute for a live terminal-cleanup acceptance/regression. If the old failure recurs, develop against Playwright Host, not `extension/`.
- Branch `fix/148-cleaner-lane-residue` pinned HEAD `23f88a942bca7bdd2ae1d4f8cb08b3325f43b379` removed via [cah-shot run 39096257715](https://github.com/Tests4gptplay/git-agent-harness/actions/runs/39096257715). Run status `completed/success`; remote ref re-read confirms absence.
- Total CAH refs now **9**: `main` plus eight retained refs; two open PRs (#330, #349). Net removals since 74-ref inventory: **65**.

### Eight retained non-main branch refs and reasons

| Branch | Pinned SHA | Retention rationale / next gate |
|---|---|---|
| \`docs/draco-cn14-three-way-case-384\` | \`199147df9e6da4c451b32f99a31eeacd9dd3d23a\` | Issue #384 open; independent migration results and candidate Skill adjustments absent on main. Inspect accepted deliverable + whether evidence should enter Skill or separate task archive before considering deletion. |
| \`fix/327-worker-lease-helper-recovery\` | \`1bba29aab4d6b99b586e36329dd319c793fd5625\` | Issue #327 open; 11 unique commits and historical worker_recovery.py absent on main; current lifecycle has evolved. Requires semantic diff against modern Helper/watchdog behavior before deciding reuse/discard. |
| \`fix/329-conversation-load-retry\` | \`0407a0286dc803bae07fc3ea11822e6dda69b6f3\` | Draft PR #330 open; adds bound ChatGPT retry handling and tests not observed on main. Rebase/redesign/test against current Playwright before merge/close. |
| \`fix/348-planner-turn-ceiling\` | \`fb27dc33d6e134b6b94113fe1a3894d86c74b969\` | Draft PR #349 open; current main uses prompt_count/prompt_ceiling, PR counts completed semantic Planner turns. Related but *not identical*. Require policy choice and regression comparison before closing/merging. |
| \`release/public-1.0.4-verified\` | \`885a87f7a73e338b0156d5ffe5fd0d212e4a37e4\` | 13 unique commits, publication/verification/export scripts distinct from other release line. Public v1.0.4 is tagged and released with ZIP/asset digest but does not replace private build history. KEEP. |
| \`release/public-1.0.4\` | \`886fed8d862e995671324a7d4e48ca7b966dfedb\` | 13 unique commits, public overlay/export/publish tooling distinct from verified release line. KEEP. |
| \`showcase/viewer-v18-preview-001-cooked-exec\` | \`33eb996f6c155b51fda579ba5e35e6a537103712\` | 131 unique commits, distinct cooked Viewer tools/code/execution evidence not on main. User reports Viewer task completed; preserve for reproducibility. KEEP. |
| \`work/viewer-v18-preview-001-native\` | \`41d1a735405133f2a186bea769eed15455c5fa90\` | 119 unique commits, independent native Viewer workline differs from cooked branch. KEEP. |

### Post-action boundary

- `state/chatgpt.json` read-only check: `active_task=world-execute-chatgpt-showcase-20261017`, `phase=RUNNING`. No managed task state edited by cleanup.
- **No release or Viewer branch deletion.** No changes to separate MMCA/Cache research repositories.
- New write to CAH main was limited to the existing reusable `.github/workflows/foreground-direct-command.yml` slot to run exact guarded deletion. No new branch created.
- Closing #149 does not certify completion of Issue #148. Unresolved PRs #330/#349 and task branches #327/#384 require explicit technical evaluation rather than mass cleanup.
