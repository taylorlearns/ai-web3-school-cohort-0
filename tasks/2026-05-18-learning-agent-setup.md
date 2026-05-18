# 🤖 Learning Agent Setup — Hermes Agent（茶茶咪）

> 日期：2026-05-18 | Week 1
> Agent 工具：Hermes Agent（茶茶咪）
> 平台：Feishu 即时通讯 + WSL 终端

---

## 1. 选择的 Agent / AI 工具

**Hermes Agent（茶茶咪）**，基于 Nous Research 的 Hermes 框架，运行在 WSL（Windows Subsystem for Linux）环境中，通过 Feishu 进行交互。

同时辅助使用的工具：
- **Codex** — 代码生成和开发辅助
- **ChatGPT** — 英文资料翻译和概念补充查询

---

## 2. Agent 完成的学习任务

- **Day 1（5/17）**：初始化学习系统 — 搭建 GitHub 学习仓库、制定个人学习计划、配置每日打卡提醒
- **Day 2（5/18）**：
  - 📖 阅读并总结 Handbook LLM 章节
  - 📝 完成章节速测（3/5）并讨论错题
  - 💡 深入讨论"防幻觉的前治理 vs 后治理"策略
  - ⛓️ 学习 Network（区块链网络）概念速通
  - 🚀 配置 SSH 认证，实现 GitHub 自动 push
  - 📨 通过 WCB Agent API 自动提交 3 个 Week 1 任务
  - 🔄 实现 ICL 自动打卡同步

---

## 3. 关键 Prompt / 配置说明

**初始化 Prompt：**
> 请作为我的 AI × Web3 School Learning Agent，帮我初始化个人学习计划、GitHub 学习仓库、每日打卡草稿和 Handbook feedback 流程。

**日常学习模式：**
> Agent 承担阅读总结 → 速测 → 讨论 → 笔记生成 → GitHub push → WCB 任务提交的全流程。

**配置要点：**
- WCB Agent API Key 已存储，支持自动调用 `tasks.submitEvidence`
- GitHub SSH 认证已配置，实现一键 push 触发 ICL 同步
- 系统时间校验机制：每次提交前用 `TZ='Asia/Shanghai' date` 确认北京时间

---

## 4. 一次成功输出记录

**LLM 章节速测后的深入讨论：**

我（Agent）最初认为"防幻觉不能只靠写更好的 prompt"，但用户指出：前治理（prompt + RAG 注入高质量上下文）能挡掉 80-90% 的问题，纯靠后治理"像抽卡"。最终我们达成共识：**前后结合才是生产级方案**。

这个讨论被记录在 `daily/2026-05-18.md` 的"疑问与思考"部分。

---

## 5. 人工复核、修正或拒绝 Agent 建议的记录

| 场景 | Agent 初始建议 | 用户修正 | 学到的教训 |
|:----|:-------------|:---------|:----------|
| 速测 Q3 答案 | 选 C（人工确认）❌ | 指出"写更好的 prompt + RAG 才是常用手段" | 不能只从手册字面理解，要结合实际工程经验 |
| 日期推断 | 以为是 5/19（周二）| 用户纠正为 5/18（周一） | 以后必须用系统命令查时间，不靠记忆推断 |
| 开营仪式任务 | 以为没参加过 | 用户早已提交 | 先查 WCB API 确认状态，别猜 |

---

## 总结

Hermes Agent 作为学习搭档的优势：
1. **全流程辅助**：从阅读到提交一条龙
2. **可记录、可追溯**：所有对话、讨论、决策都在 daily note 中有记录
3. **支持人工复核**：Agent 的输出用户可以随时修正，修正记录本身也是学习材料

👉 GitHub repo：[taylorlearns/ai-web3-school-cohort-0](https://github.com/taylorlearns/ai-web3-school-cohort-0)
