# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Spendly** is a personal finance/expense tracker web application built with Flask. It allows users to log expenses, categorize spending, and view breakdowns by category and time period.

## Commands

```bash
# Run the application
python app.py

# Run tests
pytest

# Run a specific test
pytest -k test_name

# Activate virtual environment (if needed)
source venv/bin/activate  # macOS/Linux
```

## Architecture

- **Framework**: Flask 3.1 with Werkzeug 3.1
- **Database**: SQLite (connection via `database/db.py`)
- **Testing**: pytest + pytest-flask
- **Frontend**: Jinja2 templates + vanilla CSS/JavaScript

### File Structure

```
expense-tracker/
├── app.py              # Flask application with routes
├── database/
│   ├── __init__.py     # Package init (empty)
│   └── db.py           # Database utilities (get_db, init_db, seed_db)
├── templates/
│   ├── base.html       # Base template with navbar/footer
│   ├── landing.html    # Landing page
│   ├── register.html   # Registration form
│   └── login.html      # Login form
├── static/
│   ├── css/style.css   # Styles
│   └── js/main.js      # JavaScript (currently empty scaffold)
└── requirements.txt    # Dependencies
```

### Routes

| Route | Status | Description |
|-------|--------|-------------|
| `/` | Implemented | Landing page |
| `/register` | Implemented (UI only) | Registration form |
| `/login` | Implemented (UI only) | Login form |
| `/logout` | Stub | Returns placeholder |
| `/profile` | Stub | Returns placeholder |
| `/expenses/add` | Stub | Returns placeholder |
| `/expenses/<id>/edit` | Stub | Returns placeholder |
| `/expenses/<id>/delete` | Stub | Returns placeholder |

### Database Layer

The `database/db.py` file is a scaffold. It needs implementation of:
- `get_db()` - Returns SQLite connection with `row_factory` and foreign keys enabled
- `init_db()` - Creates tables using `CREATE TABLE IF NOT EXISTS`
- `seed_db()` - Inserts sample development data

## Development Context

This is a **learning scaffold** - most backend logic is intentionally left unimplemented for students to build. The UI/UX is complete for landing, login, and registration pages. When implementing features, follow the "Step X" comments in `app.py` as guidance for the intended progression.
