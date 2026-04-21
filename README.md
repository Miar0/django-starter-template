# Django Starter Template

A modern, high-performance Django starter template. This project focuses on developer experience, code quality, and the latest Python tooling.

## Quick Start (Recommended)

This project uses **uv**, the fastest Python package manager. If you don't have it yet, [install it here](https://docs.astral.sh/uv/getting-started/installation/).

1. **Create a virtual environment and install dependencies:**
   ```bash
   uv venv
   # Activate: .venv\Scripts\activate (Windows) or source .venv/bin/activate (macOS/Linux)
   uv pip install -e .[dev]
   ```
   *The -e .[dev] flag installs the project in editable mode along with all development tools.*

## Alternative Installation (Standard Pip)

If you prefer the classic approach:
```bash
python -m venv venv
# Activate: .venv\Scripts\activate (Windows) or source .venv/bin/activate (macOS/Linux)
pip install -e .[dev]
```

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

## Configuration & Security

1. **Environment Variables:**
   Copy the example environment file and fill in your local settings:
   ```bash
   cp .env.example .env
   ```
2. **Secret Key:**
   **CRITICAL:** Ensure you change the SECRET_KEY in your .env file. Never commit your real secret key to version control. You can generate a new one using:
   ```bash
   python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'
   ```

## Database Setup

The project is configured for **PostgreSQL**.
1. Ensure your PostgreSQL server is running.
2. Update your database credentials in the .env file (see DB_NAME, DB_USER, etc.).
3. Run migrations:
   ```bash
   python manage.py migrate
   ```

## Updates

- **To update project dependencies:**
  ```bash
  uv pip install --upgrade -e .[dev]
  ```
- **To update pre-commit hooks:**
  ```bash
  pre-commit autoupdate
  ```
