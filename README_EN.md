# 🛠️ GitHub Skill Forge: Turn Your AI Assistant into a "Pro" Instantly

[![English](https://img.shields.io/badge/Language-English-blue?style=flat-square)](./README_EN.md)
[![简体中文](https://img.shields.io/badge/语言-简体中文-red?style=flat-square)](./README_ZH.md)

[![Trae Meta-Skill](https://img.shields.io/badge/Platform-Trae-blueviolet?style=for-the-badge&logo=probot)](https://github.com/Trae)
[![Skill-Forge](https://img.shields.io/badge/Skill-Forge-F39C12?style=for-the-badge&logo=hammer)](#)
[![Zero-Clone](https://img.shields.io/badge/Mode-Zero--Clone-2ECC71?style=for-the-badge&logo=githubactions)](#)

Found a cool project on GitHub and want your AI to help you tweak or run it, only to realize: there's too much code for the AI to read? The setup is a mess? Manually copying and pasting is a nightmare?

**GitHub Skill Forge** was built to solve these headaches. It acts as a "Skill Converter" that transforms any GitHub repository into a "Skill Package" your AI assistant (like Trae) can instantly understand and use. No manual cloning, no complex local environment setup—just provide a link, and it handles everything for you.

---

### 💡 What can it do for you?

*   **✨ Cloud-Direct (Zero-Clone)**: Scans repositories directly via GitHub API without cloning code locally, saving disk space and scanning at lightning speed.
*   **📦 Core Extraction (Smart RAG)**: Automatically filters out clutter and extracts only the core logic and documentation into an AI-specific context file (`context_bundle.md`), letting the AI grasp the project's essence instantly.
*   **⚡ Mirror Acceleration**: Built-in multiple API mirrors with automatic rotation and multi-threaded fetching to bypass GitHub's rate limits.
*   **🛡️ Quality Screening**: Automatically identifies project Stars and activity to help you avoid unfinished or "buggy" repositories.

---

### 📁 Folder Contents Explained

*   🧬 **`scripts/forge.py`**: The core execution script. All fetching, parsing, and packing work is done by this script behind the scenes.
*   📖 **`SKILL.md`**: The AI's "Operation Manual." It defines when the AI should call this tool and how to use it.
*   🔐 **`.env.example`**: Security configuration template. By setting up a GitHub Token, you get higher access frequency for a smoother experience.

---

### 🛠️ How to Use? (Multiple Ways to Call)

Whether you want to operate manually in the terminal or have the AI do it for you, here are several simple methods:

#### Method 1: Execute Manually in Terminal (Direct)
Open Trae's terminal and enter the following command:
```bash
# Basic forge command
python scripts/forge.py "https://github.com/username/repo"

# If the project is less popular (low Star count), use --force to override
python scripts/forge.py "https://github.com/username/repo" --force
```

#### Method 2: Summon AI Directly in Chat (Smartest)
You can simply tell your Trae assistant in the chat:
> "Help me turn this repo into a skill: https://github.com/username/repo"

The AI will automatically recognize and invoke the `forge.py` script to complete the task.

#### Method 3: Custom Configuration (Advanced)
You can modify the `api_mirrors` list in `scripts/forge.py` to add your own mirrors or configure multiple Tokens in `.env` for large-scale fetching needs.

---

### 🏮 Troubleshooting FAQ

*   **Q: Got a 403 Error about "Rate Limits"?**  
    A: This is GitHub's restriction on anonymous access. Get a Personal Access Token from GitHub, put it in your `.env` file, and you'll run like a VIP.
*   **Q: Connection Timeout?**  
    A: The tool automatically rotates through routes. If all mirrors fail, check your local network proxy settings.
*   **Q: Where is the generated skill package?**  
    A: Upon success, you'll find a new folder named after the repository in the `.trae/skills/` directory. Everything is inside.