# MathAgent Modeling Kit — 给 Agent 的详细自动安装指令

> [!NOTE]
> 本文件供通用 Agent（Antigravity / DSH / Claude Code / Codex / Cursor 等）读取并自动执行安装。普通用户只需在 [README](./README.md) 中复制简短的一句话指令发送给 Agent 即可。

---

## 完整安装 Prompt（可直接整段发给 Agent）

```text
请帮我全自动安装「MathAgent 数学建模通用 Agent 套件（mathagent-modeling-kit-universal）」，请严格按以下步骤执行，遇到错误先排查再汇报：

1. 下载安装包与校验文件：
   - 压缩包：https://github.com/Wuyanqiao/mathagent-modeling-kit-universal/releases/download/v1.0/mathagent-modeling-kit-universal-v1.0.zip
   - SHA-256：https://github.com/Wuyanqiao/mathagent-modeling-kit-universal/releases/download/v1.0/mathagent-modeling-kit-universal-v1.0.zip.sha256
   - 若 GitHub 直连较慢，可先检查本地代理或提示我手动下载后放到指定路径。

2. 校验完整性：
   - 校验压缩包的 SHA-256 是否与 `.sha256` 文件一致（预期值：`2da3495ae98d67df4aeece05f4ff38683b364667dbb60792d79707109511a94c`）。
   - 若校验不一致，立即停止并重新下载，切勿继续解压。

3. 解压到固定目录：
   - 目标目录：用户主目录下的 `tools/mathagent-modeling-kit`（Windows 如 `~/tools/mathagent-modeling-kit`，macOS/Linux 为 `~/tools/mathagent-modeling-kit`）。
   - 若目标目录已存在，先重命名备份（例如加上时间戳后缀）再解压。
   - 注意避免多层嵌套目录，确保目标目录内直接可见 `setup.cmd`、`setup.sh`、`requirements.txt`、`skills/` 等文件。

4. 检查 Python 并安装科学计算依赖：
   - 确认可用 Python 版本 >= 3.11。
   - 进入解压目录执行：`pip install -r requirements.txt`

5. 运行一键全端安装（自动配置 Skills + MCP + 全局 `ma` 命令）：
   - Windows：在解压目录执行 `.\setup.cmd`
   - macOS / Linux：在解压目录执行 `chmod +x setup.sh ma.sh && ./setup.sh`
   - 安装脚本会自动备份原有 Agent 配置并幂等合并，不会覆盖已有其他配置。

6. 安装后自检与汇报：
   - 执行 `ma setup --check`（若 `ma` 暂未进入当前终端 PATH，则使用解压目录下的 `.\ma.cmd setup --check` 或 `./ma.sh setup --check`）。
   - 执行 `ma doctor` 检查科学计算库与排版工具状态。
   - 向我清晰汇报：安装路径、各 Agent（Antigravity / DSH / Claude Code / Codex / Cursor）的 Skills 与 MCP 挂载状态、缺失项（如有），并提醒我**重启对应 Agent 客户端**使新技能和 MCP 生效。
   - 最后附上一句重启后的开赛起手指令：
     「请使用 math-modeling-orchestrator 技能开始数学建模，赛题和数据在 ./data/，先向我确认竞赛预设与预览台偏好。」
```
