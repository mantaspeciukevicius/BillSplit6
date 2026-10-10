# Bill Split

An early Flask foundation for a shared-expense application, created as coursework. The code in this revision implements account registration, authentication, logout and user profiles. A complete expense-splitting workflow is not implemented in this version.

## Origin

**Original creation date: 24 January 2023.** The GitHub repository and its earliest recorded commit date to this day.

The original application was created by Mantas Peciukevičius during the **Code Academy course, without AI assistance**. This statement refers to the original coursework; the portfolio documentation was refreshed later.

## Implemented features

- Registration and password hashing.
- Login/logout and session-based authentication.
- User profiles and authenticated page access.
- Persistent users in SQLite.
- A Flask application factory with separate authentication and main blueprints.

## Technology stack

| Layer | Technologies |
| --- | --- |
| Language / web framework | Python, Flask 2.2.2 |
| Database | SQLite, SQLAlchemy 1.4.46, Flask-SQLAlchemy 3.0.2 |
| Authentication | Flask-Login 0.6.2 and Werkzeug 2.2.2 password hashing |
| Templates / styling | Jinja2 3.1.2, HTML/CSS and Bulma |

Versions above were recovered from the dependency metadata committed with the historical project. The repository did not include a standalone root requirements file.

## Run locally

Create a fresh Python 3.10 environment; do not reuse the old committed `auth` or `venv` directories:

```sh
python3.10 -m venv .venv
# Linux / macOS
. .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
pip install Flask==2.2.2 Flask-Login==0.6.2 Flask-SQLAlchemy==3.0.2 SQLAlchemy==1.4.46 Werkzeug==2.2.2 Jinja2==3.1.2
python -c "from project import create_app, db; app = create_app(); app.app_context().push(); db.create_all()"
flask --app project run --host 127.0.0.1
```

Open `http://127.0.0.1:5000`, register a local account, and try login and profile navigation. Set a fresh Flask secret key before use beyond a local demonstration.

## Repository layout

- `project/__init__.py`: factory and extension/blueprint configuration.
- `project/auth.py`: registration, login and logout.
- `project/main.py`: public and profile pages.
- `project/models.py`: user model.
- `project/templates/`: Bulma-styled Jinja pages.

Use a newly initialized database and keep runtime databases, account data and local environments out of version control.
