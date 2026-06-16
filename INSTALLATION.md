# Installation Guide

## System Requirements

- **Python**: 3.8 or higher
- **OS**: Windows, macOS, or Linux
- **RAM**: Minimum 512 MB
- **Disk Space**: ~100 MB for installation

## Step-by-Step Installation

### 1. Clone or Download the Project

```bash
cd path/to/your/projects
# If cloning from git:
# git clone <repository-url>
# Or extract the project folder manually
```

### 2. Create a Virtual Environment

Navigate to the project directory and create a virtual environment:

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Upgrade pip

```bash
python -m pip install --upgrade pip
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

This will install all required packages:
- `tkinter` - GUI framework (usually included with Python)
- `pandas` - Data analysis and manipulation
- `matplotlib` - Data visualization and charting
- `openpyxl` - Excel file handling
- `reportlab` - PDF generation
- `bcrypt` - Password hashing and verification

### 5. Verify Installation

Test if all dependencies are installed correctly:

```bash
python -c "import tkinter; import pandas; import matplotlib; import openpyxl; import reportlab; import bcrypt; print('All dependencies installed successfully!')"
```

### 6. Run the Application

```bash
python main.py
```

The login window should appear. Use default credentials:
- **Username**: `admin`
- **Password**: `admin123`

## Troubleshooting

### Issue: `No module named 'tkinter'`

**Solution (Windows):**
- Reinstall Python and ensure "tcl/tk and IDLE" is checked during installation

**Solution (Ubuntu/Debian):**
```bash
sudo apt-get install python3-tk
```

**Solution (macOS):**
- Tkinter is included with Python. If missing, reinstall Python from python.org

### Issue: `ModuleNotFoundError: No module named 'bcrypt'`

Ensure you activated the virtual environment and ran `pip install -r requirements.txt`

```bash
pip install bcrypt --upgrade
```

### Issue: Permission denied when running the app

Make the script executable:

**macOS/Linux:**
```bash
chmod +x main.py
```

### Issue: Database file not created

Ensure the `database` folder exists. It will be created automatically on first run.

### Issue: Port already in use (if network features added)

Kill the process using that port or modify the port in settings.

## Docker Installation (Optional)

If you prefer using Docker:

1. Create a `Dockerfile` in the project root:

```dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "main.py"]
```

2. Build and run:

```bash
docker build -t attendance-system .
docker run -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix attendance-system
```

## Virtual Environment Management

### Deactivate Virtual Environment

```bash
deactivate
```

### Delete Virtual Environment

```bash
# On Windows
rmdir /s venv

# On macOS/Linux
rm -rf venv
```

### Update Dependencies

```bash
pip install --upgrade -r requirements.txt
```

## Next Steps

- Read [USER_GUIDE.md](USER_GUIDE.md) to learn how to use the application
- Check [README.md](README.md) for project overview
- Review the code structure and modules in `gui/` and `database/` folders
