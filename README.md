# 🚀 LangChain Basic — Modern AI Project Setup (UV-Based)

This project provides a **clean, modern foundation** for building LangChain-based AI applications.

It is designed as a starting point for:

- 🔹 LLM integrations (OpenAI, Gemini, etc.)
- 🔹 Retrieval-Augmented Generation (RAG)
- 🔹 Vector database integration
- 🔹 Future agentic workflows

Instead of using legacy Python tooling (`pip`, `venv`, `requirements.txt`),  
this project uses **UV**, a modern, fast, and reproducible Python package manager.

---

# ⚡ Quick Start

```bash
git clone <your-repo-url>
cd LangChain_Basic
uv sync
source .venv/Scripts/activate   # Git Bash
```

You are now ready to build.

---

# 🐍 Python Version

This project requires:

```
Python >= 3.12
```

Check your version:

```bash
python --version
```

If needed, install Python 3.12 before proceeding.

---

# 📦 Why UV Instead of pip?

Instead of:

- `pip`
- `python -m venv`
- `requirements.txt`

We use:

- ✅ `uv`
- ✅ `pyproject.toml`
- ✅ `uv.lock`

UV provides:

- ⚡ Faster dependency resolution
- 🔁 Automatic virtual environment management
- 🔒 Locked, reproducible builds
- 🧠 Modern Python project standards

---

# 🛠 Installation & Setup (Step-by-Step)

---

## 1️⃣ Install UV

```bash
pip install uv
```

This installs the modern Python package manager.

---

## 2️⃣ Initialize the Project

```bash
uv init
```

This creates:

- `pyproject.toml`
- Project metadata
- Python version constraints

Similar to:

- `npm init` (Node.js)
- `gradle init` (Java)

---

## 3️⃣ Add LangChain Dependency

```bash
uv add langchain
```

This:

- Installs LangChain
- Updates `pyproject.toml`
- Updates `uv.lock`
- Prepares environment for sync

---

## 4️⃣ Sync Dependencies & Create Virtual Environment

```bash
uv sync
```

This command:

- Creates `.venv`
- Installs dependencies
- Uses `uv.lock` for exact versions
- Ensures reproducible builds

Example output:

```
Using CPython 3.12.x
Creating virtual environment at: .venv
```

---

## 5️⃣ Activate Virtual Environment

### If using Git Bash:

```bash
source .venv/Scripts/activate
```

### If using PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

If activated correctly, your terminal will show:

```
(langchain-basic)
```

That means:

- Virtual environment is active
- Python now uses `.venv`

---

# 🔐 Environment Variables & Security

---

## 6️⃣ Create `.env` File

In the project root, create:

```
.env
```

Add your OpenAI API key:

```env
OPENAI_API_KEY="sk-proj-xxxxxxxxxxxxxxxx"
```

---

## ⚠️ VERY IMPORTANT SECURITY NOTE

**Always add `.env` to your `.gitignore` file.**

Open `.gitignore` and add:

```
.env
```

If `.gitignore` does not exist, create it.

### Why?

- `.env` contains secret API keys
- Committing it to GitHub exposes your credentials
- Exposed keys can lead to billing abuse
- Providers may disable leaked keys

---

## 🔒 Best Practices

Never:

- ❌ Hardcode API keys inside Python files
- ❌ Push `.env` to GitHub
- ❌ Share API keys publicly

Always:

- ✅ Use environment variables
- ✅ Use `python-dotenv`
- ✅ Keep secrets outside source code

Security is mandatory in real-world development.

---

# 🧠 Load Environment Variables in Python

Install dotenv:

```bash
uv add python-dotenv
```

Then use:

```python
from dotenv import load_dotenv
import os

load_dotenv()

api_key = os.getenv("OPENAI_API_KEY")
print(api_key)
```

---

# 🌿 Optional: Rename Git Branch to `main`

```bash
git branch -m main
```

Modern Git standard uses `main` instead of `master`.

---

# 📂 Project Structure

```
LangChain_Basic/
│
├── .venv/
├── pyproject.toml
├── uv.lock
├── .env
├── .gitignore
├── main.py
└── README.md
```

---

# 🔥 Modern Workflow Summary

```bash
pip install uv
uv init
uv add langchain
uv sync
source .venv/Scripts/activate   # Git Bash
```

---

# 🧩 Why This Is Better Than Old pip + venv

| Old Way | Modern UV Way |
|----------|---------------|
| python -m venv venv | uv sync |
| pip install | uv add |
| requirements.txt | pyproject.toml |
| pip freeze | uv.lock |

Cleaner. Faster. Reproducible.

---

# 🚀 What’s Next?

You can now extend this foundation to:

- 🔹 Build LangChain applications
- 🔹 Add OpenAI or Gemini models
- 🔹 Implement RAG pipelines
- 🔹 Integrate vector databases (FAISS, Chroma, Milvus)
- 🔹 Build agentic workflows

This repository serves as a clean architectural base for AI development.

Langchain

First install uv-->pip install uv
1. uv init
2. In order to initialize vertual environment, we can 'uv venv .venv' but I can say
'uv sync', this command is a special command, it will create .venv and sync all dependencies. >>>uv sync 
Using GitBash>>> $ uv sync Using CPython 3.12.12 Creating virtual environment at: .venv
3. git branch -m main
4. uv add langchain
5. For Git Bash 'source .venv/Scripts/activate' for Powershell '.venv/Scripts/activate'
6. Create .env file in root folder
7. Add key and value for OpenAI in .env file like==>OPENAI_API_KEY="sk-proj"
8. uv add langchain_openai
9. uv add langchain_core
10. We have deticated library for prompt
11. uv add load-dotenv

🧱 Pydantic vs TypedDict — When and Why to Use

In modern AI systems (LLMs, RAG, Agents, APIs), defining and validating structured data is critical.

Python provides two approaches:

- TypedDict — lightweight static typing (no runtime validation)
- Pydantic — runtime validation and enforcement (recommended for production)

📘 TypedDict (Static Type Hinting)

TypedDict defines the expected structure of a dictionary for static type checking.

```python
from typing import TypedDict

class CountrySchema(TypedDict):
    capital: str
    country: str