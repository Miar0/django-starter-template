# Django Starter Template

A modern, high-performance Django starter template. This project focuses on developer experience, code quality, and the latest Python tooling.

## Prerequisites & Package Manager

This project exclusively uses **uv**, a blazingly fast Python package manager written in Rust. Before starting, check if you have it installed:

```bash
uv --version
```

### Installing uv (If not installed)

If the command above is not recognized, install `uv` using one of the following official methods for your OS:

* **macOS / Linux:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
* **Windows (PowerShell):**
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

---

## Quick Start

Setting up the project environment takes just a single command.

1. **Install all dependencies and setup environment:**
```bash
uv sync
```
   *This command automatically creates an isolated virtual environment (`.venv`) and installs both core project dependencies and development tools (`[dependency-groups]`).*

2. **Activate the virtual environment:**

* **Windows (Command Prompt):**
```cmd
.venv\Scripts\activate
```
* **macOS / Linux:**
```bash
source .venv/bin/activate
```

---

## Code Quality & Pre-commit

We use **Ruff** for linting and formatting. It replaces Flake8, Isort, and Black with a single, blazingly fast tool.

1. **Set up git hooks (required after cloning):**
```bash
pre-commit install
```

2. **Run checks manually on all files:**
```bash
pre-commit run --all-files
```

---

## Configuration & Security

1. **Environment Variables:**
   Copy the example environment file and fill in your local settings:
```bash
cp .env.example .env
```
2. **Secret Key:**
   **CRITICAL:** Ensure you change the `SECRET_KEY` in your `.env` file. Never commit your real secret key to version control. You can generate a new one using:
```bash
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
```

---

## Database Setup

The project is configured for **PostgreSQL**.
1. Ensure your PostgreSQL server is running.
2. Update your database credentials in the `.env` file (see `DB_NAME`, `DB_USER`, etc.).
3. Run migrations:
```bash
python manage.py migrate
```

---

## Updates

- **To update project dependencies and sync lockfile:**
```bash
uv lock --upgrade && uv sync
```
- **To update pre-commit hooks:**
```bash
pre-commit autoupdate
```