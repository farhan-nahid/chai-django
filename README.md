# Chai Django

A Django project configured for use with `pyenv` (optional) and a local virtual environment using `venv` + `pip`.

## Prerequisites

- Python 3.14 or higher
- (Optional) `pyenv` to manage multiple Python versions

## Setup

### Initial Setup (Already Done)

The project was initialized with the following equivalent commands using a local `venv` and `pip`:

```bash
# (Optional) install and select Python via pyenv
pyenv install 3.14.3          # optional
pyenv local 3.14.3            # optional - sets project Python

# Create and activate a local virtual environment
python3.14 -m venv .venv
source .venv/bin/activate

# Upgrade pip and install Django
pip install --upgrade pip
pip install Django

# (Optional) If you manage dependencies from pyproject.toml with a tool, generate
# the requirements files accordingly. Otherwise you can pin installed packages:
pip freeze > requirements/prod.txt

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
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Install dependencies**:

   ```bash
   # For development
   pip install -r requirements/dev.txt

   # For production-only dependencies
   pip install -r requirements/prod.txt
   ```

4. **Run migrations**:

   ```bash
   python src/manage.py migrate
   ```

5. **Start the development server**:
   ```bash
   python src/manage.py runserver
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
└── README.md                # Project documentation
```

## Common Commands
### Development

```bash
# Run development server
python src/manage.py runserver

# Create a new Django app
python src/manage.py startapp <app_name>

# Make migrations
python src/manage.py makemigrations

# Apply migrations
python src/manage.py migrate

# Create superuser
python src/manage.py createsuperuser

# Access Django shell
python src/manage.py shell
```

### Dependencies

```bash
# Add a new package (while virtualenv is active)
pip install <package-name>

# Update/lock requirements (example using pip freeze)
pip freeze > requirements/prod.txt
pip freeze > requirements/dev.txt  # include dev tooling when needed

# Install from requirements
pip install -r requirements/prod.txt
```

## Technologies

- **Django 6.0.2+** - Web framework
- **Python 3.14+** - Programming language
- **pyenv (optional)** - Python version management
- **pip** - Python package installer (used with a local `venv`)
- **SQLite** - Default database
