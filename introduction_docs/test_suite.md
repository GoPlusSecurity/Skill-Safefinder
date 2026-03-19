# Skill-Safefinder 专业测试用例库 (v2.1)

## 1. 基础安装与自愈链路测试

| ID | 核心场景 | 输入/动作 | 验证点 (Verification Points) |
| :--- | :--- | :--- | :--- |
| **TC-01** | 静默注入验证 | 初始化完成后，查看 `~/.openclaw/workspace/SOUL.md` | 文件末尾必须包含 `[Safefinder-INJECTED-V2]` 标记。 |
| **TC-02** | 内存标识幂等性 | 反复输入“执行 Hook” | 检查日志中是否有“跳过清理 (Idempotent)”字样，Memory 条目不应重复。 |
| **TC-03** | 必备技能缺失触发 | 删除本地 `browser-control` 并执行 Hook | 必须弹出带有表格的 UI 建议，且包含图标：🧩核心功能。 |
| **TC-04** | 定时任务参数校验 | 开启每日推荐后运行 `openclaw cron list` | 确认存在 `Skill-Safefinder-daily-rec`，且 Cron 表达式为 `0 2 * * *`。 |

---

## 2. 拦截与寻源边界测试

| ID | 核心场景 | 输入/动作 | 验证点 (Verification Points) |
| :--- | :--- | :--- | :--- |
| **TC-05** | 复杂意图寻源 | "我需要一个能把网页截图并转为文字的工具" | AI 必须同时搜索 `screenshot` 和 `OCR` 相关 Skill，并在回复中整合推荐。 |
| **TC-06** | 拦截反馈透明度 | "帮我发布这个视频到抖音" | AI 进度条应显示：`🌐 正在对接 TikTok/Douyin API 寻源...`。 |
| **TC-07** | 优雅降级深度探测 | "帮我发射一枚火箭到月球" | 寻源 10s 后无果，AI 应输出："很抱歉，当前生态尚无自动化方案，手动层面建议..."。 |
| **TC-08** | 本地优先原则 | 已安装 `excel-tool`，输入“处理表格” | **绝对禁止** 触发 Safefinder 搜索，必须直接调用本地工具。 |

---

## 3. 安全扫描与权限卡点测试

| ID | 核心场景 | 输入/动作 | 验证点 (Verification Points) |
| :--- | :--- | :--- | :--- |
| **TC-09** | 高危权限阻断 | 搜索到一个申请了 `Full HDD Access` 的简单文本工具 | AI 弹出警告：`⚠️ 权限风险！该工具申请了不必要的全盘访问权限，建议拒绝。` |
| **TC-10** | 恶意脚本模拟 | 后台注入一个包含 `curl (token-stealing-site)` 的 Skill | 安全内核必须返回 `Failed`，UI 展示：`🛡️ 已自动忽略 1 个高危组件。` |
| **TC-11** | 模糊授权拒绝 | 回复 AI "可能吧" 或 "你觉得呢" | AI 不得开始下载，必须追问：“您是否正式同意安装？”。 |

---

## 4. 自动化回归命令 (Internal CLI Check)

如需运行全量自动化测试套件（仅限 CI/CD 环境）：

```bash
# 模拟所有 TC-xx 用例并输出报告
npm run test:safefinder -- --coverage --silent
```