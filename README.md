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
uv pip compile pyproject.toml -o requirements.txt
django-admin startproject core
```

### Getting Started

1. **Clone the repository** (if not already done):

   ```bash
   git clone <repository-url>
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
├── src/
│   ├── core/              # Django project settings
│   ├── manage.py          # Django management script
│   └── db.sqlite3         # SQLite database
├── main.py                # Entry point script
├── pyproject.toml         # Project dependencies
├── requirements.txt       # Compiled requirements
└── README.md              # This file
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
uv pip compile pyproject.toml -o requirements.txt

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
