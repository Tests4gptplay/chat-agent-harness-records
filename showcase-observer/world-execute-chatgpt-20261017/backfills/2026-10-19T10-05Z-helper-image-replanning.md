# 2026-10-19 后续缺口核对：Worker 恢复、原生生图与重新规划

- 补记时间：2026-10-19T10:06:00Z。
- 取证截止：源仓库 commit `ddf5f7b628ccf9db59c3d07603954099a9153f42`（2026-10-19T10:05:06Z）。
- 用户明确要求核对独立记录库并补充后续任务记录。本次只写私有记录库，不修改或调度 CAH。
- 核对已有树：最后独立事件为 03:11Z；最后 hourly 为 02:00Z。03:11Z 后存在记录缺口。本文件是事后按持久证据补记，**不伪造逐小时现场观察**，也不声称完整重建缺口中的每一步。
- 原 README 的 append-only / 非干预规则保持；既有快照、冷归档 INDEX.json 均不改。

## 1. 旧执行链的真实推进与两种不同恢复

早期 G1 仍标 RUNNING，但 Helper 报告 Host 实际绑定在已完成前驱对话，watchdog 已解除。该报告记录首轮残留标签页导致去重再次引用已删聊天、随后关闭精确残留标签页并恢复同一 G1 身份。此处是直接读到 Helper 的持久报告，观察者没有再次访问本地浏览器；不能包装成观察者亲自执行的恢复。Actions 39206344695、39207350567、39207868619 为报告引用的核验链。原 Child Reply 随后记下九次真实 in-band CAH Tool 调用，证实 self 浏览器传输/点击；仍没有实际图片或 Windows 导入。

之后旧 G2 出现未闭合工具调用（BEGIN、无 END/RESULT）；Helper 报告一次原地 Retry 未推进，早期删除检查因 sidebar 匹配不唯一而在修改前中止。不能把该 selector 歧义等同平台删除拒绝。经精确定位，Actions 39223545762 报告删除唯一旧聊天；同代恢复保留 dispatch/generation/fence/wake。报告记录 08:36:26Z 新物理 response-start、39224205300 检查 watchdog ARMED；随后清除已过时的 manual Regenerate / WAIT_USER，恢复 WAIT_RESULT。这个阶段只证明恢复链和工具继续，不证明生图或 MV 完成。

## 2. Foreground 纠正和 Planner 接收

- rev10：先实际调用当前可用的第一方图片能力，生成后再处理保存；不把外部 API 或提前完成下载验证作为生成前提。旧 Child Reply 保存了非派发 REVIEW，避免对仍运行的 G2 重复派图。
- rev11：仅允许新生成、非敏感原创测试图经已有 private Git → 正式本地拉取；覆盖旧 Child 的禁止图片进 Git 限定，不包括歌曲、歌词、秘密或公开发布。旧 Reply 指向 Child 合约更新 commit `05531ffbd6d71064c5268533fdfb251c3b470460`。
- Canonical inbox 中 rev11 event `event-8956426866e2990c4ef2edd7856f99af` 于 09:27:49Z 被 CONSUMED；Formal Plan v9 实际记载这一通道。授权/计划已更新，不代表 Git 图片传输已实测成功。

## 3. 后一次 Helper：用户停止旧 G2，不再同代替换

Helper `worker-helper-f06b696ee6aab842a64d09b0` 报告：G2 曾取得多次真实浏览器结果，最后 image-mode-select 调用没有匹配结果；看到创建图像选中标记，尚无成图。Host 重启未补回结果。用户随后明确要求停止该 Worker、修复状态并反馈 Planner。

持久报告记录 Actions 39230312955 核实 Worker 已 idle、只关闭精确标签页（保留聊天历史），commit `33732f6b41d92ab3f1a2c6e796547f5d8fae41b4` 将该 G2 canonical RUNNING 改 CANCELLED，没有伪造 Worker Result；39230950840 同步 local final_signal 并验证 Host 恢复；`8fb0dd4a55afed5ff1491ddb7f90590ba8457463` 恢复 toolbox neutral no-op。
Canonical inbox 显示取消事件 09:43:39Z 消费、Helper result 09:48:45Z 消费。旧 Child Reply 有 Planner RETIRE_CANCELLED_NOT_ACCEPT。取消的是旧分支，原 MV Parent 未被取消。

## 4. 新 Child 确实生图，但未获得合格艺术源

`child-1d319a650df7f62d6735c9ca` 于 09:44:44Z 获 response-start，09:51:04Z backend 为 BLOCKED。Worker ledger 报告一次 image_gen.text2im 调用与原始 PNG：
- 1448×1086，RGB，1,532,122 字节。
- SHA256 `5f999eb4615877cc008c0edcfaa67b85123991d1a9592fd652fa4359a657cf51`。
- Worker 所见内容为合成 GitHub/code UI，不是电影式原创母图；返回 metadata 的 prompt 为空。

证据层级：观察者确认 ledger / Result / CL 已落 Git；PNG 字节与像素描述来自 Worker 实测报告。Planner 明确只读报告，未亲自打开 transient 原图。这里不能宣称 Planner 独立美术验收，更不能由 prompt metadata 为空推断用户描述必然模糊、模型根本不能生图，或已查明提交参数根因。

该输出被判不适合作为艺术源：Git 图片上传未尝试，本地拉取未尝试，正式 native960/practical480 QA、分层、H264、V2 都未发生。**内容失败没有否定 Git 二进制传输方案。** “一次额度已耗尽”是当前任务合约/Planner 的预算解释，不是平台账户全局生图额度耗尽的证据。

## 5. 新规划已从草稿推进到派发，但成果尚待验证

09:52:01Z Planner 认领新生图结果事件；10:04:16Z CONSUMED。Formal Plan v10、Plan Note 与同轮 outcome=CONTINUE / turn_signal=done 均已落盘：
- 将失败图片分支退役；当前不再自动追加生图。
- 用已有工具做不同的空间/动态排版与2.5D电影表达，选择一个真实歌曲 cue，设计两个不同的“之前→选择→后果”方案。
- 每个方案先三张真实关键帧（原生最高960、实用480）；均不合格就 ART_NO_GO。
- 只有关键帧有实际质量，才允许 ≥25 张真实连续源时钟帧；此时仍不允许直接长片 V2 或最终 A4 PASS。

截至固定 commit，新的 `child-893a343aef58574811d59d8b` 已在 lane-00 建立，10:05:06Z backend RUNNING，dispatch `dispatch-b644695bf06d1715fa265996`，G1，ack_source=extension_response_start；semantic_work 与 branch_output 仍 WAIT、result_ref=null。因此这是“已派发并开始响应”，不能说已完成六张图或25帧，更不能说重规划已经解决审美问题。Parent 仍 PARKED_WAIT_EVENT / WAIT_RESULT，未终态。

## 观察判断及未闭环

恢复机制确实保留了任务证据和身份并允许用户停止旧路线、由 Planner 接手新规划；但此前工具执行中断与之后艺术源不合格是两类问题，不能统称“纯粹规划争论”或全部归因程序错误。当前新媒体路线是否真的改善质量，要看真实产物。原有完整 V1 技术基线仍保留，A4 艺术与最终 A1–A8 验收没有因此通过；本次未重新测量本地原片/音频/154哈希。后续优先核对新 Child 的真实关键帧与 Planner 亲见审查，避免把 response-start 当作产出。

## 不可变来源

- old_reply: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/memory/worker/child-a52c3269aed3ce919bf69dce/reply.md
- g1_recovery: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/evidence/world-execute-chatgpt-showcase-20261017/roles/helper/planner-helper-f01656ab850d7e38ffc9077e.json
- g2_recovery: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/evidence/world-execute-chatgpt-showcase-20261017/roles/helper/worker-helper-996a9bca82888569b005ea91.json
- g2_stop: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/evidence/world-execute-chatgpt-showcase-20261017/roles/helper/worker-helper-f06b696ee6aab842a64d09b0.json
- image_ledger: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/evidence/art-direction/p4r0-native-source-child-1d319a650df7f62d6735c9ca-g1.json
- plan: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/tasks/world-execute-chatgpt-showcase-20261017.plan.json
- plan_note: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/memory/planner/world-execute-chatgpt-showcase-20261017/plan_note.md
- state: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/state/task_cells/world-execute-chatgpt-showcase-20261017.json
- direction: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/state/planner_turns/world-execute-chatgpt-showcase-20261017/doorbell-679fdcdc22a281930f22f5b09c0641c6/worker-slot-1.json
- outcome: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/state/planner_turns/world-execute-chatgpt-showcase-20261017/doorbell-679fdcdc22a281930f22f5b09c0641c6/outcome.json
- new_cl: https://github.com/Tests4gptplay/git-agent-harness/blob/ddf5f7b628ccf9db59c3d07603954099a9153f42/cl/child-893a343aef58574811d59d8b.backend.json

本次未复制图像、原始音频、歌词、私人聊天全文或凭据；只追加时间线、状态、必要哈希与来源。没有写入源执行仓库、唤醒角色或触发本地操作。
