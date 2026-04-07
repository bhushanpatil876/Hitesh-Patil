# Flask To-Do List Application 📝

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/bhushanpatil876/Hitesh-Patil/actions)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Database Design (SQLAlchemy)](#database-design-sqlalchemy)
- [Installation & Setup](#installation--setup)
- [How It Works](#how-it-works)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

This is a To-Do List web application built using **Python Flask** and **SQLAlchemy**. It allows users to add, update, and delete tasks in a simple and user-friendly interface. The app uses Flask as the web framework and SQLAlchemy as the ORM for database management, making it easy to manage tasks efficiently.

---

## Features

- ✅ **Add New Tasks** – Quickly add new tasks using the input box.
- ✅ **Mark Tasks as Complete** – Mark tasks as completed with a simple checkbox.
- ✅ **Update/Edit Tasks** – Update task names directly from the interface.
- ✅ **Delete Tasks** – Remove unneeded tasks with a delete button.
- ✅ **Simple and Clean User Interface** – Responsive design with Bootstrap for a great user experience.

---

## Technologies Used

| Technology | Purpose |
|---|---|
| **Python 3.x** | Backend programming language |
| **Flask** | Web framework for routing and request handling |
| **Flask-SQLAlchemy** | ORM for database operations |
| **SQLite** | Lightweight database |
| **HTML / CSS / Bootstrap** | Frontend design and responsiveness |

---

## Prerequisites

Before you begin, ensure you have the following installed:
- **Python 3.8 or higher** – [Download Python](https://www.python.org/downloads/)
- **pip** – Python package manager (comes with Python)
- **Git** – [Download Git](https://git-scm.com/)

---

## Database Design (SQLAlchemy)

The application uses **SQLAlchemy ORM** to manage the database with a clean and efficient schema.

### Task Model

```python
from flask_sqlalchemy import SQLAlchemy

db = SQLAlchemy()

class Task(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    title = db.Column(db.String(100), nullable=False)
    complete = db.Column(db.Boolean, default=False)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    def __repr__(self):
        return f'<Task {self.id}: {self.title}>'
```

### Schema Details

| Column | Type | Description |
|--------|------|-------------|
| **id** | Integer (Primary Key) | Unique identifier for each task |
| **title** | String(100) | Text/title of the task (required) |
| **complete** | Boolean | Tracks if the task is completed (default: False) |
| **created_at** | DateTime | Timestamp when the task was created |

---

## Installation & Setup

Follow these steps to set up and run the Flask To-Do List application:

### 1. Clone the Repository

```bash
git clone https://github.com/bhushanpatil876/Hitesh-Patil.git
cd Hitesh-Patil
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate Virtual Environment

**Windows:**
```bash
venv\Scripts\activate
```

**Mac/Linux:**
```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

**Expected dependencies (requirements.txt):**
```
Flask==2.3.0
Flask-SQLAlchemy==3.0.0
```

### 5. Initialize the Database

```bash
python
>>> from app import app, db
>>> with app.app_context():
...     db.create_all()
>>> exit()
```

### 6. Run the Flask Application

```bash
python app.py
```

### 7. Open Your Browser

Navigate to `http://127.0.0.1:5000` to view the application.

---

## How It Works

### Application Flow

1. **Home Page** – Displays all tasks from the SQLite database with their completion status.
2. **Add Task** – Enter a task title and click "Add". This creates a new Task entry in the database.
3. **Mark Complete/Incomplete** – Click a checkbox to toggle the task's completion status in real-time.
4. **Update Task** – Edit the task title and save changes to the database.
5. **Delete Task** – Remove the task from the database permanently.

### CRUD Operations

All CRUD (Create, Read, Update, Delete) operations are handled using:
- **Flask Routes** – Define endpoints for each operation
- **SQLAlchemy Queries** – Execute database transactions
- **Jinja2 Templates** – Render dynamic HTML responses

---

## Deployment

### Deploy to Heroku

1. **Create a Heroku Account**
   - Sign up at [Heroku](https://www.heroku.com/)

2. **Install Heroku CLI**
   - [Download Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

3. **Login to Heroku**
   ```bash
   heroku login
   ```

4. **Create a Procfile**
   ```
   web: gunicorn app:app
   ```

5. **Deploy the Application**
   ```bash
   heroku create your-app-name
   git push heroku main
   heroku open
   ```

### Deploy to Render or Other Platforms

Refer to their respective documentation for deployment steps.

---

## Contributing

We welcome contributions to improve this project! Here's how you can help:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/bhushanpatil876/Hitesh-Patil.git
   ```

2. **Create a New Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Changes and Commit**
   ```bash
   git add .
   git commit -m "Add your descriptive message"
   ```

4. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**
   - Submit a Pull Request with a detailed description of your changes.

---

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## Questions or Issues?

If you have any questions or encounter issues, feel free to:
- Open an [Issue](https://github.com/bhushanpatil876/Hitesh-Patil/issues)
- Create a [Discussion](https://github.com/bhushanpatil876/Hitesh-Patil/discussions)

---

**Happy Coding! 🚀**
