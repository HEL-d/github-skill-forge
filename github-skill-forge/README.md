<div align="center">

# 🛠️ GitHub Skill Forge (GitHub 技能锻造厂)

[![Trae Meta-Skill](https://img.shields.io/badge/Trae-Meta--Skill-blueviolet?style=for-the-badge&logo=ai)](https://github.com/Trae)
[![Automation](https://img.shields.io/badge/Task-Automation-green?style=for-the-badge&logo=github)](#)
[![Zero-Clone](https://img.shields.io/badge/Mode-Zero--Clone-orange?style=for-the-badge&logo=git)](#)

<br>

### 💡 这是什么？
**GitHub Skill Forge** 是你的 AI 助手（如 Trae Agent）的“超能力扩展器”。它不仅仅是一个脚本，而是一个**元技能（Meta-Skill）**——一个专门用来制造“技能”的技能。

当你在 GitHub 上发现一个很酷的工具，但懒得去手动克隆、看文档、配环境时，这个工具就是你的救星。它能自动帮你把任意 GitHub 仓库转化为 Trae Agent 可以直接理解并使用的**标准化技能包**。

### 🚀 核心超能力
- **✨ 零克隆模式 (Zero-Clone)**：直接通过 GitHub API 扫描，不占用硬盘就能生成技能。适合快速探索和轻量級集成。
- **📦 智能聚合 (Lite-RAG)**：把散乱的代码、README、依赖项“浓缩”成一个 `context_bundle.md`，让 AI 一眼看穿项目灵魂。
- **⚡ 混合模式 (Hybrid)**：网络不给力？自动切换到最小化克隆，确保 100% 成功率。
- **🛡️ 安全守卫**：自动检查项目 Stars 数，避开不成熟的“坑”。
- **🎨 标准化输出**：自动生成标准的目录结构，让你的技能库整齐划一。

### 🏗️ 技术架构
锻造厂由以下核心逻辑驅動：
1. **API 镜像矩阵**：内置多组 GitHub API 镜像，自動輪換以繞過速率限制（Rate Limit）。
2. **多執行緒抓取**：使用 `ThreadPoolExecutor` 同步抓取多個核心代碼文件。
3. **智能語言識別**：自動解析 `package.json`、`requirements.txt` 等文件，精確判斷項目技術棧。
4. **動態模板引擎**：根據抓取到的信息，自動生成量身定制的 `SKILL.md` 指南。

### 📁 目录文件详解
- **`scripts/forge.py`**：核心大脑 🧠。
  - `make_api_request()`: 處理帶有自動重試和鏡像輪換的 API 請求。
  - `online_repo_scanner()`: 核心掃描邏輯，遞迴檢索目錄樹。
  - `create_context_bundle()`: 聚合代碼與文檔，生成 AI 易讀的上下文。
- **`SKILL.md`**：技能说明书 📖。定義了鍛造廠本身的角色，告訴 Trae 什麼時候該召喚它。
- **`.env.example`**：安全配置模板 🔐。教你如何安全地配置 GitHub Token 以獲得更快的 API 訪問權限。

### 🛠️ 怎么用？
只需一行指令，就能把 GitHub 上的工具据为己有：
```bash
# 基礎用法
python .trae/skills/github-skill-forge/scripts/forge.py "https://github.com/作者/项目名"

# 強制模式 (忽略安全檢查)
python .trae/skills/github-skill-forge/scripts/forge.py "https://github.com/作者/项目名" --force
```

### 🏮 故障排除
- **403 Forbidden**: 通常是 API 速率限制。請在 `.env` 中配置 `GITHUB_TOKEN`。
- **SSL Error**: 網絡環境問題，腳本會自動嘗試鏡像站，若全失敗請檢查代理。

<br>


</div>
