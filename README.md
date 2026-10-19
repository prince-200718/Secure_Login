# 🔐 Secure Login System with Password Hashing

**IBM SkillsBuild Cyber Security 2026 — BharatCares**

| Field | Details |
|---|---|
| Prince H Kiazolu |
| Secure Login System with Password Hashing |
| Web Security / Authentication |
| IBM SkillsBuild Cyber Security 2026 |
 | BharatCares |

---

## 📌 Project Description

A fully functional, secure web-based login system built with **Python** and **Flask** that demonstrates five core cybersecurity concepts applied to a real-world authentication scenario:

1. **Password Hashing** — passwords are stored as bcrypt one-way hashes, never plain text
2. **Salting** — bcrypt automatically generates a unique salt per password, defeating rainbow table attacks
3. **SQL Injection Prevention** — all database queries use parameterized statements
4. **Brute-force Lockout** — accounts lock after 5 consecutive failed login attempts
5. **Session Management** — server-side Flask sessions restrict access to authenticated users only

Users can **register**, **log in**, view a **protected dashboard**, and **log out**. The system provides real-time feedback on failed attempts and account lockout status.

---

## 🗂️ Project Structure

```
secure-login/
├── app.py                          ← Main Flask application (all routes + security logic)
├── database.py                     ← SQLite database initialization
├── requirements.txt                ← Python dependencies
├── StudentName_SecureLoginSystem.ipynb  ← Jupyter Notebook (code + explanations + tests)
├── StudentName_ProjectReport.docx  ← Full project report (Word document)
├── README.md                       ← This file
└── templates/
    ├── register.html               ← User registration page
    ├── login.html                  ← Login page with lockout feedback
    └── dashboard.html              ← Protected page (requires login)
```

---

## 🛠️ Technologies Used

| Technology | Version | Purpose |
|---|---|---|
| Python | 3.10+ | Primary programming language |
| Flask | 3.1.3 | Web framework |
| Flask-Bcrypt | 1.0.1 | Password hashing |
| bcrypt | 5.0.0 | Core hashing algorithm |
| SQLite | Built-in | Local database |
| Jinja2 | 3.1.6 | HTML templating (bundled with Flask) |

---

## ⚙️ Setup & Run Instructions

### Prerequisites
- Python 3.10 or higher installed ([python.org](https://www.python.org/downloads/))
- macOS Terminal (or any terminal on Windows/Linux)

### Step 1 — Navigate to the project folder
```bash
cd ~/Desktop/"untitled folder"/secure-login
```

### Step 2 — Activate the virtual environment
```bash
source venv/bin/activate
```
> On Windows: `venv\Scripts\activate`

### Step 3 — (First time only) Install dependencies
```bash
pip install -r requirements.txt
```

### Step 4 — Run the application
```bash
python3 app.py
```

### Step 5 — Open in browser
Go to: **http://127.0.0.1:5000**

### Step 6 — Stop the server
Press `Ctrl + C` in the terminal.

---

## 🔗 Dataset / External Resources

This project does not use an external dataset — it generates its own data via user registration stored in a local SQLite file (`users.db`) created automatically on first run.

**Relevant resources:**
- [OWASP Top 10](https://owasp.org/www-project-top-ten/) — Web application security risks
- [Flask Documentation](https://flask.palletsprojects.com/) — Web framework
- [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) — Password hashing algorithm
- [NIST SP 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html) — Digital Identity Guidelines

---

## 🔑 Key Security Features

### Password Hashing & Salting
```python
# Hash a password (auto-salted by bcrypt)
hashed_pw = bcrypt.generate_password_hash(password).decode("utf-8")

# Verify a password against its hash
bcrypt.check_password_hash(stored_hash, entered_password)
```

### SQL Injection Prevention
```python
# ❌ VULNERABLE — never do this
query = f"SELECT * FROM users WHERE username = '{username}'"

# ✅ SAFE — parameterized query (what this app uses)
conn.execute("SELECT * FROM users WHERE username = ?", (username,))
```

### Brute-force Lockout
```python
MAX_ATTEMPTS = 5  # Account locks after 5 failed attempts
```

---

## 📋 Application Routes

| Route | Method | Description |
|---|---|---|
| `/` | GET | Redirects to login |
| `/register` | GET, POST | User registration |
| `/login` | GET, POST | User login with attempt tracking |
| `/dashboard` | GET | Protected page (requires session) |
| `/logout` | GET | Clears session |

---

## 📁 Submission Files

| File | Format | Description |
|---|---|---|
| `SecureLoginSystem.ipynb` | `.ipynb` | Jupyter Notebook with all code, demos, and tests |
| `ProjectReport.docx` | `.docx` | Full project documentation report |
| `README.md` | `.md` | This overview file |
| `requirements.txt` | `.txt` | Python library dependencies |

---

## 👤 Author

Prince Kiazolu
IBM SkillsBuild Cyber Security 2026 — BharatCares
