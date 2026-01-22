<div align="center">

# 🛠️ GitHub Skill Forge

[![Trae Meta-Skill](https://img.shields.io/badge/Trae-Meta--Skill-blueviolet?style=for-the-badge&logo=ai)](https://github.com/Trae)
[![Automation](https://img.shields.io/badge/Task-Automation-green?style=for-the-badge&logo=github)](#)
[![Zero-Clone](https://img.shields.io/badge/Mode-Zero--Clone-orange?style=for-the-badge&logo=git)](#)

<br>

### 💡 What is this?
**GitHub Skill Forge** is the "Superpower Expander" for your AI assistants (like Trae Agent). It's more than just a script; it's a **Meta-Skill** — a skill designed specifically to forge other skills.

When you find a cool tool on GitHub but don't want to manually clone, read docs, or configure environments, this is your lifesaver. It automatically transforms any GitHub repository into a **standardized skill package** that Trae Agent can directly understand and utilize.

### 🚀 Core Superpowers
- **✨ Zero-Clone Mode**: Scans directly via GitHub API, generating skills without consuming local disk space. Perfect for quick exploration.
- **📦 Smart Aggregation (Lite-RAG)**: Condenses scattered code, READMEs, and dependencies into a single `context_bundle.md`, allowing AI to grasp the project's soul instantly.
- **⚡ Hybrid Mode**: Network issues? Automatically falls back to minimized cloning to ensure 100% success rate.
- **🛡️ Security Guard**: Automatically checks project Stars to avoid immature or risky projects.
- **🎨 Standardized Output**: Automatically generates a standard directory structure to keep your skill library organized.

### 🏗️ Technical Architecture
The Forge is driven by several core logic components:
1. **API Mirror Matrix**: Built-in multiple GitHub API mirrors with automatic rotation to bypass Rate Limits.
2. **Multi-threaded Scraping**: Uses `ThreadPoolExecutor` to fetch multiple core code files concurrently.
3. **Smart Language Detection**: Automatically parses files like `package.json` and `requirements.txt` to precisely determine the tech stack.
4. **Dynamic Template Engine**: Automatically generates a tailored `SKILL.md` guide based on the scraped information.

### 📁 Directory & File Details
- **`scripts/forge.py`**: The Core Brain 🧠.
  - `make_api_request()`: Handles API requests with auto-retry and mirror rotation.
  - `online_repo_scanner()`: Core scanning logic, recursively retrieving directory trees.
  - `create_context_bundle()`: Aggregates code and docs into AI-readable context.
- **`SKILL.md`**: The Skill Manual 📖. Defines the Forge's role and tells Trae when to summon it.
- **`.env.example`**: Security Config Template 🔐. Guides you on how to safely configure GitHub Tokens for faster API access.

### 🛠️ How to use?
Take ownership of any GitHub tool with just one command:
```bash
# Basic Usage
python .trae/skills/github-skill-forge/scripts/forge.py "https://github.com/user/repo"

# Force Mode (Ignore safety checks)
python .trae/skills/github-skill-forge/scripts/forge.py "https://github.com/user/repo" --force
```

### 🏮 Troubleshooting
- **403 Forbidden**: Usually an API rate limit issue. Please configure `GITHUB_TOKEN` in your `.env` file.
- **SSL Error**: Network environment issues. The script will try mirror sites automatically; if all fail, check your proxy settings.

<br>

---
*Forged with ❤️ by Little Code Sauce for LO*

</div>
