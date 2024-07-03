# 0x02. i18n

## Overview

This project focuses on internationalization (i18n) in a Flask web application. You'll learn to display content in multiple languages and handle various locales and timezones using Flask-Babel.

### Project Timeline
- **Start Date**: July 2, 2024, 6:00 AM
- **End Date**: July 3, 2024, 6:00 AM
- **Checker Release**: July 2, 2024, 12:00 PM
- **Manual QA Review**: Request upon completion before the deadline.
- **Auto Review**: Triggered at the deadline.

## Learning Objectives

- Parametrize Flask templates for multiple languages.
- Infer the correct locale from URL parameters, user settings, or request headers.
- Localize timestamps effectively.

## Requirements

- **Environment**: Ubuntu 18.04 LTS
- **Python**: 3.7
- **Style**: Pycodestyle (version 2.5)
- **Executable Files**: All Python files should be executable.
- **Documentation**: Required for all modules, classes, functions, and methods.
- **Type Annotations**: All functions and coroutines must be type-annotated.

## Setup

### Basic Flask App

Create a basic Flask app with a single `/` route and a simple HTML template.

- **File**: `0-app.py`
- **Template**: `templates/0-index.html`

### Basic Babel Setup

Install and configure Flask-Babel:

1. Install Babel:
   ```bash
   pip3 install flask_babel==2.0.0
   ```

2. Setup Babel in the Flask app and configure languages.

- **File**: `1-app.py`
- **Template**: `templates/1-index.html`

### Get Locale from Request

Implement a `get_locale` function to determine the best match for supported languages using `request.accept_languages`.

- **File**: `2-app.py`
- **Template**: `templates/2-index.html`

### Parametrize Templates

Use the `_` or `gettext` function to parametrize your templates. Create a `babel.cfg` file and initialize translations.

1. Create `babel.cfg`:

    ```text
    [python: **.py]
    [jinja2: **/templates/**.html]
    extensions=jinja2.ext.autoescape,jinja2.ext.with_
    ```

2. Extract and initialize translations:
   ```bash
   pybabel extract -F babel.cfg -o messages.pot .
   pybabel init -i messages.pot -d translations -l en
   pybabel init -i messages.pot -d translations -l fr
   ```

3. Edit translation files and compile:
   ```bash
   pybabel compile -d translations
   ```

- **Files**: 
  - `3-app.py`
  - `babel.cfg`
  - `templates/3-index.html`
  - `translations/*/LC_MESSAGES/messages.{po,mo}`

### Force Locale with URL Parameter

Modify `get_locale` to check for a `locale` URL parameter and use it if valid.

- **File**: `4-app.py`
- **Template**: `templates/4-index.html`

### Mock Logging In

Mock user login with a predefined user table and display personalized messages based on login status.

- **File**: `5-app.py`
- **Template**: `templates/5-index.html`

### Use User Locale

Update `get_locale` to prioritize locale from URL parameters, user settings, request headers, and finally, default locale.

- **File**: `6-app.py`
- **Template**: `templates/6-index.html`

### Infer Appropriate Time Zone

Create a `get_timezone` function to determine the timezone from URL parameters, user settings, or default to UTC. Validate the timezone using `pytz`.

- **File**: `7-app.py`
- **Template**: `templates/7-index.html`

### Display the Current Time

Show the current time on the home page based on the inferred timezone, formatted according to the locale.

- **Files**:
  - `app.py`
  - `templates/index.html`
  - `translations/*/LC_MESSAGES/messages.{po,mo}`

## Repository

- **GitHub Repository**: `alx-backend`
- **Directory**: `0x02-i18n`

## License

© 2024 ALX, All rights reserved.
