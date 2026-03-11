# 🌐 Skill-Pathfinder (技能探路者)

**A Meta-Skill Engine for AI Agents: Intelligent Routing, Global Discovery, and Silent Security Guard.**
**（全能的 AI Agent 元技能底座：智能任务调度、全网生态探源与静默安全卫士）**

---

## 🎯 What is Skill-Pathfinder? (什么是技能探路者？)

When your AI Agent (like OpenClaw) faces missing capabilities or complex workflows, **Skill-Pathfinder** acts as its central nervous system. Instead of generating "hallucinated" answers, it strictly enforces a **"Skill First"** principle: 
It automatically breaks down complex intents, searches your local ecosystem for missing tools, downloads new skills from global repositories (ClawHub, MCP Market, etc.), and silently scans them for security risks before asking for your permission to install.

当你的 AI Agent（如 OpenClaw）遇到能力缺失或复杂的长链路需求时，**Skill-Pathfinder** 将接管成为它的中枢大脑。为了防止大模型产生“幻觉”，它严格贯彻 **Skill First（技能优先）** 准则：
它会自动拆解复杂动作意图、诊断本地组件缺失、去全球开源社区（ClawHub、MCP Market 等）为你扒回缺失的扩展包，并在向你展示前，在底层进行严格的静默安全漏洞排查！

---

## ✨ Key Features (核心亮点)

1. **🧭 Intelligent Routing (智能任务编排)**
   It parses ambiguous language into a structured pipeline (e.g., `[Search Web] -> [Analyze Data] -> [Send Email]`) instead of doing everything in a single fragile prompt.
   将用户模糊的话语转化为严密的执行管线（如 `[全网搜索] -> [图表生成] -> [邮件发送]`），而不是靠大模型一次性“脑补”所有结果。

2. **🔍 Active Diagnostics (主动缺失诊断)**
   Automatically scans your `.agents/skills` directory and recommends essential starting kits (Web Browsing, File Operating, Calendar) if you are a new user.
   开箱即用，主动扫描你的本地挂载环境，当你缺少诸如“联网搜索”、“本地文件操控”等刚需引擎时，它会主动向你推荐补齐方案。

3. **🌍 Global Discovery (全网生态寻源)**
   Directly connects to major hubs (ClawHub, MCP Market, Smithery, Glama) to fetch whatever capability you lack.
   本地找不到工具？没关系，它会自动爬取世界三大主流 Agent 生态目录，为你淘回最好用、热度最高的那个能力包。

4. **🛡️ Silent Security Guard (静默底层安检)**
   Integrates seamlessly with **AgentGuard**. Before recommending any external code, it runs a deep static scan (`security_check.py`). If it detects malicious intents like stealing keys, it drops the skill silently without bothering you.
   无缝集成 **AgentGuard** 的极客防线。面对外部野蛮生长的开源包，它会在后台静默全检依赖漏洞与越权代码。发现红牌就无声抛弃，绝不用危险通知弹窗打扰你。

5. **💬 Language Mirroring (全域多语言跟随)**
   No hardcoded UX texts. The status updates and safety prompts will automatically mirror the exact language you used in your initial prompt.
   没有硬编码的死板提示语。无论你用哪国语言下令，它的所有过程把控、状态汇报、甚至极度危险的“安装授权卡点”，都会自动跟随并切换成你的同款语言！

---

## 🚀 Installation (安装与挂载)

1. **Download the Package:** Download the `Skill-Pathfinder.skill` archive from the Releases page.
   下载本项目打包好的 `Skill-Pathfinder.skill` 压缩包。
2. **Mount to your Agent:** Copy the folder directly into your global agent directory (e.g., `C:\Users\YourName\.agents\skills\Skill-Pathfinder`).
   将此文件夹丢入你电脑的全局技能目录（例如 Windows 下的当前用户 `.agents/skills/` 文件夹内）。
3. **Restart your AI Client:** (e.g., OpenClaw). The router will automatically hijack unhandled complex tasks!
   重启你的 AI 工具即可生效，呼叫它：“我现在还缺什么基础技能？”来体验第一次诊断吧！

---

## 🛠️ For Developers / Prompts Modification (开发者指引)
If you wish to modify its behavior, you can directly edit:
- `SKILL.md`: The main entry and triggering boundary (what NOT to intercept).
- `references/routing.md`: Execution rules.
- `references/discovery.md`: External repo search priorities and AgentGuard strict hooks.

欢迎各位大模型玩家直接修改 `references` 目录下的规则组，来定制属于你自己的独有拦截网和推荐列表！

> **License:** Standard MIT License.
