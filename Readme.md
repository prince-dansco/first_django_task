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



Why does Django separate them?

Django separates concerns to follow the core software engineering philosophy of high cohesion and loose coupling.

A Project is a complete website configuration. It represents the global infrastructure (the database connections, routing configurations, and security configurations).

An App is an isolated, self-sufficient package that performs exactly one specific function (e.g., a blogging engine, a payment system, or a contact form).

What are the benefits?

Plug-and-Play Reusability: You can extract a well-written "blog" app out of an old project and drop it into a completely new project without rewiring global settings.

Team Collaboration: Multiple developers can work simultaneously on the same website without stepping on each other's toes. 

One developer can build out features inside the payments app while another refines the forum app.

Organised Code Base: Codebases stay compact and searchable. Instead of navigating a giant file with thousands of lines of models, logic is split into logical folders.