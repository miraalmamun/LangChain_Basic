# 🚀 LangChain Basic (Modern Setup with UV)

This project demonstrates a **basic LangChain setup** using the modern Python package manager **uv**.

Instead of using:
- `pip`
- `venv`
- `requirements.txt`

We use:

- ✅ `uv`
- ✅ `pyproject.toml`
- ✅ `uv.lock`

This is the modern and recommended Python workflow.

---

# 📦 1. Install UV

Install `uv` globally:

```bash
pip install uv
```

### Why?
`uv` replaces:
- pip
- manual virtual environment creation
- requirements.txt

It is:
- Faster
- Cleaner
- Automatically manages `.venv`
- Locks dependencies properly

---

# 🏗 2. Initialize Project

```bash
uv init
```

### What this does:
- Creates `pyproject.toml`
- Defines project metadata
- Sets Python version requirement
- Prepares modern project structure

This is similar to:
- `npm init` (Node)
- `gradle init` (Java)

---

# 🔄 3. Create Virtual Environment + Sync Dependencies

Instead of manually running:

```bash
uv venv .venv
```

Use the modern command:

```bash
uv sync
```

### Why `uv sync`?

`uv sync`:
- Creates `.venv`
- Installs all dependencies from `pyproject.toml`
- Uses `uv.lock` for exact versions
- Keeps environment reproducible

Example output:

```
Using CPython 3.12.x
Creating virtual environment at: .venv
```

---

# 🌿 4. Rename Git Branch (Optional but Recommended)

```bash
git branch -m main
```

Modern Git uses `main` instead of `master`.

---

# 📚 5. Add LangChain Dependency

```bash
uv add langchain
```

This:
- Installs LangChain
- Updates `pyproject.toml`
- Updates `uv.lock`
- Syncs `.venv`

This replaces:

```bash
pip install langchain
```

But in a safer and cleaner way.

---

# ▶️ 6. Activate Virtual Environment

After `uv sync`, activate the environment.

## If using Git Bash:

```bash
source .venv/Scripts/activate
```

## If using PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

## How to confirm?

You will see:

```
(langchain-basic)
```

at the beginning of your terminal.

That means:
- Virtual environment is active
- Python now uses `.venv`

---

# 🔐 7. Create `.env` File (For API Keys)

Create a file in the project root:

```
.env
```

Add your OpenAI key:

```env
OPENAI_API_KEY="sk-proj-xxxxxxxxxxxxxxxx"
```

---

# 🧠 8. Load Environment Variables in Python

Install dotenv:

```bash
uv add python-dotenv
```

In your Python file:

```python
from dotenv import load_dotenv
import os

load_dotenv()

api_key = os.getenv("OPENAI_API_KEY")
print(api_key)
```

---

# 📂 Project Structure

```
LangChain_Basic/
│
├── .venv/
├── pyproject.toml
├── uv.lock
├── .env
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

# ✅ You Are Ready

Now you can:

- Build LangChain apps
- Add LLM integrations
- Extend to RAG
- Add vector databases

This is a clean, modern Python AI project setup 🚀


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