# Odoo Developer Task (Beginner)

## 🎯 Goal
Build a simple Odoo module with:
- A **Teacher** model
- A **Student** model
- Basic fields
- XML views for each model

This task is for beginners with basic Python and database knowledge.
All code must be only pushed to the task-implementation branch

---

## 📁 Required Module Structure

```
school/
├── __init__.py
├── __manifest__.py
├── models/
│   ├── __init__.py
│   ├── teacher.py
│   └── student.py
├── views/
│   ├── teacher_views.xml
│   └── student_views.xml
└── security/
    └── ir.model.access.csv
```

---

## 📚 Task Requirements

### 1️⃣ Create the Models

#### **Teacher (`school.teacher`)**
- `name` — Char (required)
- `email` — Char
- `phone` — Char
- `student_ids` — One2many to students

#### **Student (`school.student`)**
- `name` — Char (required)
- `age` — Integer
- `phone` — Char
- `teacher_id` — Many2one to teacher

---

### 2️⃣ Create the Views

#### Teacher Views (`teacher_views.xml`)
- List view: name, email, phone
- Form view: name, email, phone
- Notebook page with students list
- Menu item + Action

#### Student Views (`student_views.xml`)
- List view: name, age, phone, teacher
- Form view
- Menu item + Action

---

### 3️⃣ Access Rights

Take a look at the access rights file in the security
folder to gain an understanding of basic model access rights.

---

## 📦 Deliverables
- Completed `school` module
- Module must install without errors

---

## ▶️ How to Install & Test

### Step 1: Setup PostgreSQL Database
```bash
# Create a PostgreSQL user (if not exists)
sudo -u postgres createuser -s your_username

# Create a database for Odoo
createdb your_database_name
```

### Step 2: Configure Odoo
Edit your `odoo.conf` file and fill in the database credentials:
```ini
[options]
db_user = your_username
db_password = your_password
addons_path = /path/to/odoo/addons,/path/to/custom_addons
```

### Step 3: Create Python Virtual Environment
```bash
# Create virtual environment
python3 -m venv odoo-venv

# Activate the virtual environment
# On Linux/Mac:
source odoo-venv/bin/activate

# On Windows:
odoo-venv\Scripts\activate
```

### Step 4: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 5: Run Odoo
```bash
./odoo-bin -d your_database_name -c odoo.conf
```

### Step 6: Install the Module
1. Open your browser and go to `http://localhost:8069`
2. Login with admin credentials
3. Go to **Apps** menu
4. Click **Update Apps List**
5. Search for "School" module
6. Click **Install**

---

## 📘 Useful Resources

### Odoo Documentation
- [Odoo Framework Developer Guide](https://www.odoo.com/documentation/19.0/developer/tutorials/server_framework_101.html)
- [Odoo ORM Documentation](https://www.odoo.com/documentation/19.0/developer/reference/backend/orm.html#models)

### PostgreSQL Setup
- [PostgreSQL Installation Video Tutorial](https://www.youtube.com/watch?v=SpfIwlAYaKk&t=123s)
- [PostgreSQL Download Link](https://www.postgresql.org/download/)

### Important Concepts
- [Short MVC Introduction](https://www.youtube.com/watch?v=DUg2SWWK18I)
- [What is an ORM?](https://www.youtube.com/watch?v=W_pzAbqNAVw)
- [Python Virtual Environments](https://www.youtube.com/watch?v=Y21OR1OPC9A)

---

## 🧮 Evaluation Criteria

| Area | Points |
|------|--------|
| Module Structure | 20 |
| Models | 20 |
| Views | 30 |
| Access Rights | 10 |
| Code Quality | 10 |
| Successful Installation | 10 |

**Total: 100 points**

---

## ✅ End of Task
