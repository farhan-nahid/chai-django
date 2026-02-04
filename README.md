# Chai Django

A Django project bootstrapped with `uv` package manager.

## Prerequisites

- Python 3.14 or higher
- [uv](https://docs.astral.sh/uv/) package manager

## Setup

### Initial Setup (Already Done)

The project was initialized with the following commands:

```bash
uv init .
uv venv --python python3.14
source .venv/bin/activate
uv add Django
uv pip compile pyproject.toml -o requirements/prod.txt
uv pip compile pyproject.toml --group dev -o requirements/dev.txt
django-admin startproject core
```

### Getting Started

1. **Clone the repository** (if not already done):

   ```bash
   git clone git@github.com:farhan-nahid/chai-django.git
   cd chai-django
   ```

2. **Create and activate virtual environment**:

   ```bash
   uv venv --python python3.14
   source .venv/bin/activate
   ```

3. **Install dependencies**:

   ```bash
   uv sync
   ```

4. **Run migrations**:

   ```bash
   uv run python src/manage.py migrate
   ```

5. **Start the development server**:
   ```bash
   uv run python src/manage.py runserver
   ```

The server will be available at `http://127.0.0.1:8000/`

## Project Structure

```
chai-django/
├── requirements/
│   ├── dev.txt              # Development dependencies (linting, formatting, tooling)
│   └── prod.txt             # Production dependencies only
├── src/
│   ├── core/                # Django project settings and configuration
│   ├── manage.py            # Django management command entry point
│   └── db.sqlite3           # Local SQLite database (development only)
├── .gitignore               # Git ignore rules
├── .python-version          # Python version used by the project (pyenv / uv)
├── pyproject.toml           # Project metadata and dependency definitions
└── README.md                # Project documentation
```

## Common Commands

### Development

```bash
# Run development server
uv run python src/manage.py runserver

# Create a new Django app
uv run python src/manage.py startapp <app_name>

# Make migrations
uv run python src/manage.py makemigrations

# Apply migrations
uv run python src/manage.py migrate

# Create superuser
uv run python src/manage.py createsuperuser

# Access Django shell
uv run python src/manage.py shell
```

### Dependencies

```bash
# Add a new package
uv add <package-name>

# Update requirements.txt
uv pip compile pyproject.toml -o requirements/prod.txt
uv pip compile pyproject.toml --group dev -o requirements/dev.txt

# Sync dependencies
uv sync
```

## Technologies

- **Django 6.0.2+** - Web framework
- **Python 3.14+** - Programming language
- **uv** - Fast Python package installer and resolver
- **SQLite** - Default database

## License

Add your license information here.
