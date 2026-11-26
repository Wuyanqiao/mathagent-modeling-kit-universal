<div align="center">

# MathAgent Modeling Kit

**数学建模竞赛通用 Agent 套件 · Antigravity / DSH / Claude Code / Codex / Cursor 通用**

[![Release](https://img.shields.io/github/v/release/Wuyanqiao/mathagent-modeling-kit-universal?label=release)](https://github.com/Wuyanqiao/mathagent-modeling-kit-universal/releases/latest)
![Agents](https://img.shields.io/badge/agents-Antigravity%20%7C%20DSH%20%7C%20Claude%20Code%20%7C%20Codex%20%7C%20Cursor-blue)
![Python](https://img.shields.io/badge/python-3.11%2B-3776AB)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)

</div>

---

## 🤖 一句话让 Agent 帮你安装（推荐）

把下面这段话**原样复制**发给你的 Agent（Antigravity / DSH / Claude Code / Codex / Cursor 均可），它会自动完成下载、校验、解压、安装依赖和全端配置：

```text
请帮我安装 MathAgent 数学建模通用 Agent 套件：从 https://github.com/Wuyanqiao/mathagent-modeling-kit-universal/releases/download/v1.0/mathagent-modeling-kit-universal-v1.0.zip 下载压缩包，并用同一 Release 中的 mathagent-modeling-kit-universal-v1.0.zip.sha256 校验 SHA-256；解压到用户目录下的 tools/mathagent-modeling-kit（若已存在先备份）；在解压目录用 Python 3.11+ 执行 pip install -r requirements.txt；然后运行一键安装（Windows 执行 .\setup.cmd，macOS/Linux 先 chmod +x setup.sh ma.sh 再执行 ./setup.sh）；最后运行 ma setup --check，把各 Agent 的 Skills 与 MCP 就绪情况汇报给我，并提醒我重启 Agent。
```

> [!TIP]
> 安装完成后重启 Agent，在比赛目录说一句：
> **「请使用 math-modeling-orchestrator 技能开始数学建模，赛题和数据在 ./data/，先向我确认竞赛预设与预览台偏好。」**

---

## 📦 下载

| 文件 | 说明 |
|---|---|
| [`mathagent-modeling-kit-universal-v1.0.zip`](https://github.com/Wuyanqiao/mathagent-modeling-kit-universal/releases/download/v1.0/mathagent-modeling-kit-universal-v1.0.zip) | 套件本体（约 274 MB，解压后约 395 MB） |
| [`mathagent-modeling-kit-universal-v1.0.zip.sha256`](https://github.com/Wuyanqiao/mathagent-modeling-kit-universal/releases/download/v1.0/mathagent-modeling-kit-universal-v1.0.zip.sha256) | SHA-256 校验文件 |

```text
SHA256: 2da3495ae98d67df4aeece05f4ff38683b364667dbb60792d79707109511a94c
```

<details>
<summary>如何校验下载文件</summary>

```powershell
# Windows (PowerShell)
Get-FileHash .\mathagent-modeling-kit-universal-v1.0.zip -Algorithm SHA256
```

```bash
# macOS / Linux
shasum -a 256 -c mathagent-modeling-kit-universal-v1.0.zip.sha256
```

</details>

---

## 🛠️ 手动安装（4 步）

**1. 解压**：将 `mathagent-modeling-kit-universal-v1.0.zip` 解压到任意目录（例如 `D:\Tools\mathagent-modeling-kit`，建议路径不含空格和特殊符号）。

**2. 安装科学计算依赖**（需要 Python 3.11+）：在解压目录打开终端执行

```bash
pip install -r requirements.txt
```

**3. 一键全端安装**（自动备份原配置，再写入 Skills + MCP + 全局 `ma` 命令）：

```powershell
# Windows
.\setup.cmd
```

```bash
# macOS / Linux
chmod +x setup.sh ma.sh
./setup.sh
```

**4. 重启 Agent 并开始使用**：重启 Antigravity / DSH / Claude Code / Codex / Cursor，在比赛目录发一句：

> 「请使用 `math-modeling-orchestrator` 技能开始数学建模，赛题和数据在 `./data/`，先向我确认竞赛预设与预览台偏好。」

> [!NOTE]
> 如果你手里有原版 `MathAgent-3.1.0-portable.zip`，把它放在套件目录的**同级目录**再运行 `setup.cmd`，会自动抽取离线 307 包 Python、draw.io、pandoc（缺 `xelatex` 时还会抽取 TeX Live），这样第 2 步可以跳过。

---

## ✅ 安装后会配置什么

| Agent | Skills 目录 | MCP 配置 |
|---|---|---|
| Antigravity | `~/.gemini/config/skills/` | `~/.gemini/config/mcp_config.json` |
| DSH (DeepSeek Harness) | `~/.dsh/skills/` | `~/.dsh/profiles/*/cordis.patch.yml` |
| Claude Code | `~/.claude/skills/` | `~/.claude.json` |
| Codex CLI | `~/.codex/skills/` | `~/.codex/config.toml` |
| Cursor | `~/.cursor/skills-cursor/` | `~/.cursor/mcp.json` |
| 通用标准目录 | `~/.agents/skills/` | — |

只会写入检测到的 Agent；修改前会备份原配置（`*.before-mathagent-YYYYMMDD.bak`）。

---

## ✨ 包含的能力

- **23 套竞赛技能**：以 `math-modeling-orchestrator` 为总控，开始前用问答收集竞赛预设、赛题数据位置、绘图方案和预览台偏好，串起赛题分析 → 建模 → 编程求解 → 科研制图 → 论文撰写（LaTeX / Word）→ 编译终审六个阶段。
- **14 个轻量 MCP 工具**：图表配方、图示模板、顶会构图参考、文献检索、质量门禁、视觉质检、进度上报、实时预览等。
- **实时成果预览台**：浏览器每 2 秒刷新六阶段进度、文档、PDF/Word、图表和门禁结果；全自动模式下也能看进度。即使开始时没打开，产出第一个成果时也会自动打开。
- **离线资产**：265 套数据图配方、188 套竞赛图示模板、2535 张顶会构图参考图、16 套竞赛模板（国赛 / 美赛 / 华为杯 / MathorCup / 亚太杯 / 统计建模等）和内置 Word 排版引擎。

---

## ⌨️ 常用命令

```bash
ma setup --check                     # 查看各 Agent 的 Skills / MCP / 运行时状态
ma doctor                            # 体检 Python 科学库、LaTeX、draw.io、资产库
ma init ./contest --preset cumcm     # 初始化比赛工作区（16 种预设）
ma preview . --background --open     # 打开实时成果预览台
ma status .                          # 终端查看进度
ma gate all                          # 运行全部质量门禁
ma setup --uninstall                 # 卸载所有 Agent 中的 Skills 与 MCP（保留备份）
```

---

## ❓ 常见问题

<details>
<summary><b>重启后 Agent 里看不到技能或 MCP 工具？</b></summary>

运行 `ma setup --check` 确认对应 Agent 显示 `skills=23/23 | MCP=OK`；如果不是，重新运行一次 `setup.cmd` / `./setup.sh`（可重复执行）。

</details>

<details>
<summary><b>提示找不到 <code>ma</code> 命令？</b></summary>

直接用套件目录里的 `ma.cmd`（Windows）或 `./ma.sh`（macOS/Linux），或者确认执行 `pip install` 的 Python 的 `Scripts` / `bin` 目录在 `PATH` 中。

</details>

<details>
<summary><b>需要配置 API Key 吗？</b></summary>

不需要。建模、绘图、排版和本地质检都能离线使用。外部审稿、看图质检、AI 生图是可选功能，需要时在 `~/.mathagent/config.toml` 中填写 `base_url` 和 `api_key`。

</details>
