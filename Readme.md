# My Portfolio Project

A clean Django web application engineered to showcase structural deployment and implementation of MVT patterns.



  [ USER BROWSER ] 
         │  ▲
 1. URL  │  │ 6. HTML Response
 Request │  │
         ▼  │
   [ urls.py (Router) ]
         │
 2. Maps │
 Request │
         ▼
    [ views.py (Controller/Logic) ]
     │ ▲                 │ ▲
     │ │                 │ │
3.   │ │ 4. Data         │ │ 5. Renders
Data │ │ Returns         │ │    Data Into
Req  ▼ │                 ▼ │    Template
  [ models.py ]       [ templates/ ]
  (Database)          (HTML/CSS/JS)



## Core File Descriptions

* **`manage.py`**: A command-line management wrapper script. It handles local project interactions such as starting development servers (`runserver`), executing database migrations (`migrate`), and initializing internal applications (`startapp`).
* **`settings.py`**: The global configuration hub of the project. It declares active pluggable components (`INSTALLED_APPS`), security authentication credentials (`SECRET_KEY`), database connection drivers (`DATABASES`), and asset directory paths.

## Complete Django Project Setup Guide

Follow these exact steps to recreate this Django development ecosystem from scratch:

### Step 1: Initialize Workspace & Environment
```bash
# Create and navigate to project directory
mkdir my_portfolio_project && cd my_portfolio_project

# Set up an isolated Python environment
python -m venv .venv

# Activate environment (Windows PowerShell)
.venv\Scripts\Activate.ps1
# Activate environment (Mac/Linux)
source .venv/bin/activate
```

### Step 2: Install Dependencies & Build Structure
```bash
# Install core Django framework packages
python -m pip install django

# Initialize the main project folder in the current directory
python -m django startproject main_page .

# Build a modular application component
python manage.py startapp blog
```

### Step 3: Global Configurations
1. Open `my_portfolio_project/settings.py`.
2. Locate the `INSTALLED_APPS` array.
3. Append `'blog',` to the array to link the new app to the system core.

### Step 4: Fire Up Server
```bash
# Launch local testing engine
python manage.py runserver
```
Visit `http://127.0.0` in any browser to confirm execution.
