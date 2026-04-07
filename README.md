#Flask To-Do List Application 📝

**Project Overview**

This is a To-Do List web application built using Python Flask and SQLAlchemy. It allows users to add, update, and delete tasks in a simple and user-friendly interface. The app uses Flask as the web framework for routing and rendering HTML templates.

**Features**
- Add new tasks
- Mark tasks as completed
- Update or edit tasks
- Delete tasks
- Simple and clean user interface

**Technologies Used**
- Python 3.x
- Flask – Web framework
- Flask SQLAlchemy – ORM for database operations
- HTML / CSS / Bootstrap – Frontend design
- SQLite – Database

**Database Design (SQLAlchemy)**

The application uses SQLAlchemy ORM to manage the database.

**Task Model**
```python
from flask_sqlalchemy import SQLAlchemy

db = SQLAlchemy()

class Task(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    title = db.Column(db.String(100), nullable=False)
    complete = db.Column(db.Boolean, default=False)
```

- **id:** Unique identifier for each task
- **title:** Text of the task
- **complete:** Boolean to track if the task is done

**Installation & Setup**

1. **Clone the repository**
   ```bash
   git clone <your-repo-link>
   cd flask-todo
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   ```

3. **Activate virtual environment**
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - Mac/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Run the Flask application**
   ```bash
   python app.py
   ```

6. **Open your browser and go to** `http://127.0.0.1:5000`

**How It Works**

- **Home Page** – Displays all tasks from the database.
- **Add Task** – Enter a task and click "Add". This creates a new Task entry in the database.
- **Mark Complete / Incomplete** – Click a checkbox to toggle task status.
- **Update Task** – Edit the task title and save changes.
- **Delete Task** – Remove the task from the database.

All CRUD operations are handled using Flask routes and SQLAlchemy queries.
