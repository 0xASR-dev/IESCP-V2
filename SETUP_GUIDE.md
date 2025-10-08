# Quick Setup Guide

Get IESCP up and running in 5 minutes! 🚀

## Prerequisites Check

Before starting, ensure you have:
- ✅ Python 3.11 or higher installed
- ✅ pip (Python package manager)
- ✅ Git (for cloning the repository)
- ✅ A code editor (VS Code, PyCharm, etc.)

Check your Python version:
```bash
python --version
```

## Step-by-Step Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/22f3002042/IESC-platform.git
cd IESC-platform
```

Or download the ZIP file and extract it.

### 2️⃣ Create Virtual Environment

**Windows (PowerShell):**
```powershell
python -m venv venv
.\venv\Scripts\activate
```

**Windows (Command Prompt):**
```cmd
python -m venv venv
venv\Scripts\activate.bat
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

You should see `(venv)` in your terminal prompt.

### 3️⃣ Install Dependencies

```bash
pip install -r requirement.txt
```

This will install:
- Flask 3.0.3
- SQLAlchemy 2.0.31
- Flask-Login 0.6.3
- Flask-Migrate 4.0.7
- Flask-SQLAlchemy 3.1.1
- And other dependencies...

### 4️⃣ Initialize Database

**Option A: Using Python Shell**
```bash
python
```

Then in the Python shell:
```python
from main import app, db
with app.app_context():
    db.create_all()
exit()
```

**Option B: Using Flask Shell**
```bash
flask shell
```

Then:
```python
db.create_all()
exit()
```

You should now see `instance/iesc.db` file created.

### 5️⃣ Run the Application

```bash
python main.py
```

Or using Flask CLI:
```bash
flask run
```

You should see:
```
 * Running on http://127.0.0.1:5000
```

### 6️⃣ Access the Application

Open your browser and go to:
```
http://localhost:5000/
```

or

```
http://127.0.0.1:5000/
```

🎉 **Congratulations!** The landing page should now be displayed.

## Creating Your First Users

### Admin User (Manual Creation)

You need to create an admin user manually in the database:

**Option 1: Using Python Shell**
```python
from main import app, db
from models import User

with app.app_context():
    admin = User(
        username='admin',
        email='admin@gmail.com',
        password='admin123',  # Change this!
        role='admin',
        unflag_request=''
    )
    db.session.add(admin)
    db.session.commit()
    print("Admin user created successfully!")
```

**Option 2: Using SQLite Browser**
1. Download [DB Browser for SQLite](https://sqlitebrowser.org/)
2. Open `instance/iesc.db`
3. Go to "Browse Data" → "users" table
4. Click "New Record" and fill in:
   - username: admin
   - email: admin@gmail.com
   - password: admin123
   - role: admin
   - flagged: 0
   - unflag_request: (empty)

### Sponsor Registration

1. Go to `http://localhost:5000/`
2. Click "Sign Up" under Sponsor card
3. Fill in the form:
   - Username
   - Email
   - Password
   - Company Name
   - Industry
   - Budget
4. Click "Sign Up"
5. Login with your credentials

### Influencer Registration

1. Go to `http://localhost:5000/`
2. Click "Sign Up" under Influencer card
3. Fill in the form:
   - Username
   - Email
   - Password
   - Category (e.g., Fashion, Tech, Gaming)
   - Niche (e.g., Lifestyle, Reviews)
   - Reach (followers count)
4. Click "Sign Up"
5. Login with your credentials

## Testing the Application

### Test Admin Features
1. Login as admin
2. Navigate to Dashboard
3. Check statistics
4. Go to "Users" to manage users
5. Go to "Campaigns" to view all campaigns

### Test Sponsor Features
1. Login as sponsor
2. Create a new campaign:
   - Go to "Campaigns" → "Create Campaign"
   - Fill in details
   - Set visibility (Public/Private)
3. Search for influencers:
   - Go to "Influencer" menu
   - Use filters
4. Send ad requests

### Test Influencer Features
1. Login as influencer
2. Browse public campaigns
3. View ad requests
4. Accept/reject requests

## Troubleshooting

### Port Already in Use
If you see "Address already in use":
```bash
# Windows
netstat -ano | findstr :5000
taskkill /PID <PID> /F

# macOS/Linux
lsof -ti:5000 | xargs kill -9
```

Or use a different port:
```bash
flask run --port 5001
```

### Database Errors
If you get database errors:
1. Delete `instance/iesc.db`
2. Recreate the database (Step 4)

### Import Errors
If you get "ModuleNotFoundError":
```bash
# Make sure virtual environment is activated
pip install -r requirement.txt
```

### Template Not Found
Make sure you're running the app from the project root directory:
```bash
cd /path/to/IESC-platform
python main.py
```

### Styles Not Loading
Clear browser cache:
- Chrome/Edge: `Ctrl + Shift + Delete`
- Or use Incognito mode: `Ctrl + Shift + N`

## Development Mode

For development with auto-reload:

**Option 1: Using Flask CLI**
```bash
export FLASK_APP=main.py  # macOS/Linux
set FLASK_APP=main.py     # Windows CMD
$env:FLASK_APP="main.py"  # Windows PowerShell

export FLASK_ENV=development  # macOS/Linux
set FLASK_ENV=development     # Windows CMD
$env:FLASK_ENV="development"  # Windows PowerShell

flask run --debug
```

**Option 2: In main.py**
```python
if __name__ == '__main__':
    app.run(debug=True)
```

## Project Structure Overview

```
IESC-platform/
├── instance/           # Database storage
│   └── iesc.db        # SQLite database
├── templates/         # HTML templates
├── main.py           # Main application file
├── models.py         # Database models
├── db.py            # Database initialization
└── requirement.txt  # Dependencies
```

## Default Credentials Reference

| Role | Email | Password |
|------|-------|----------|
| Admin | admin@gmail.com | admin123 |
| Sponsor | (Create during signup) | - |
| Influencer | (Create during signup) | - |

⚠️ **Security Note**: Change default admin password after first login!

## Next Steps

1. ✅ Create test users for all roles
2. ✅ Create sample campaigns
3. ✅ Test ad request workflow
4. ✅ Explore admin features
5. ✅ Customize the platform

## Getting Help

- 📚 Read the [README.md](README.md) for detailed documentation
- 🐛 Report issues on [GitHub Issues](https://github.com/22f3002042/IESC-platform/issues)
- 💬 Ask questions in [GitHub Discussions](https://github.com/22f3002042/IESC-platform/discussions)

## Useful Commands

```bash
# Activate virtual environment
source venv/bin/activate  # macOS/Linux
.\venv\Scripts\activate   # Windows

# Deactivate virtual environment
deactivate

# Install new package
pip install package-name
pip freeze > requirement.txt  # Update requirements

# Run application
python main.py
flask run

# Open Flask shell
flask shell

# Check installed packages
pip list
```

---

**Happy Coding! 🚀**

If you found this helpful, give the project a ⭐ on GitHub!
