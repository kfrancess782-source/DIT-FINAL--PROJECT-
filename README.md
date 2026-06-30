# Attendance Tracking and Management System

A professional desktop-based Attendance Tracking and Management System built with Python Tkinter and SQLite. Perfect for educational institutions, businesses, and organizations that need to efficiently manage and track attendance records.

## 📋 Table of Contents

- [Features](#features)
- [Project Overview](#project-overview)
- [System Requirements](#system-requirements)
- [Quick Start](#quick-start)
- [Documentation](#documentation)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [License](#license)
- [Contributing](#contributing)

## ✨ Features

### Core Features Implemented

#### 🔐 Security & Authentication
- Secure login system with username/password authentication
- Password hashing using bcrypt for maximum security
- Role-based access control (Admin, Staff)
- Session management
- Forgot password functionality with reset capability

#### 📊 Dashboard
- Real-time attendance statistics
  - Total registered members
  - Members present today
  - Members absent today
- Recent attendance records (last 30 entries)
- Current date and time display
- Auto-updating dashboard

#### 👥 Member Management
- Complete CRUD operations (Create, Read, Update, Delete)
- Add new members with validation
- Update member information
- Delete member records
- Search and filter members by ID, name, or department
- Field validation:
  - Email format validation
  - Phone number validation
  - Unique ID enforcement
  - Required field validation

#### ✅ Attendance Marking
- Mark attendance with multiple status options
  - Present
  - Absent
  - Late
  - Excused
- Automatic timestamp recording
- Duplicate attendance prevention (one entry per member per day)
- Quick selection interface
- Today's attendance view

#### 📈 Reports & Analytics
- Visual pie charts for today's attendance
- Attendance statistics breakdown
- Member-wise attendance history
- Data-driven insights

#### ⚙️ Settings & Administration
- Create new user accounts with role assignment
- Change password functionality
- Database backup feature
- Restore database from backups
- Administrative control panel

### Future Enhancement Areas

- [ ] CSV/Excel file import for batch member registration
- [ ] Excel (.xlsx) export with formatted reports
- [ ] CSV export for data analysis
- [ ] PDF report generation
- [ ] QR code attendance scanning
- [ ] Barcode scanning support
- [ ] Weekly and monthly attendance reports
- [ ] Department-wise analytics dashboard
- [ ] Email report notifications
- [ ] Automatic backup scheduler
- [ ] Dark mode / Light mode toggle
- [ ] Face recognition (advanced)

## 📖 Project Overview

This system provides a complete solution for attendance tracking and management:

- **Database**: SQLite for reliable data persistence
- **Interface**: Tkinter for cross-platform GUI
- **Security**: Bcrypt for secure password storage
- **Data Visualization**: Matplotlib for charts and analytics
- **Data Processing**: Pandas for attendance analysis
- **Export**: Support for multiple formats (Excel, CSV)

The application is designed to be:
- **User-friendly**: Intuitive interface for easy adoption
- **Scalable**: Can handle large numbers of members and records
- **Secure**: Protected with password hashing and input validation
- **Maintainable**: Well-organized, documented code
- **Extensible**: Modular design for easy feature additions
- **Friendly**: system is responsive and workable making buttons working.

## 💻 System Requirements

- **Python**: 3.8 or higher
- **Operating System**: Windows, macOS, or Linux
- **RAM**: Minimum 512 MB
- **Disk Space**: ~100 MB for installation and database
- **GUI Framework**: Tkinter (included with Python)

## 🚀 Quick Start

### Installation

1. **Clone or Download** the project:
```bash
cd path/to/project
```

2. **Create Virtual Environment**:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install Dependencies**:
```bash
pip install -r requirements.txt
```

4. **Run Application**:
```bash
python main.py
```

### Default Credentials

- **Username**: `admin`
- **Password**: `admin123`

⚠️ **Important**: Change the default password on first login through the Settings module.

### Detailed Installation

For comprehensive installation instructions, see [INSTALLATION.md](INSTALLATION.md)

## 📚 Documentation

### For Users
- [USER_GUIDE.md](USER_GUIDE.md) - Complete user manual with step-by-step instructions for all features

### For Developers
- [INSTALLATION.md](INSTALLATION.md) - Technical installation and troubleshooting guide
- [CONTRIBUTING.md](CONTRIBUTING.md) - Guidelines for contributing to the project
- [LICENSE](LICENSE) - MIT License

### Quick Links
- **How to install?** → See [INSTALLATION.md](INSTALLATION.md)
- **How to use the app?** → See [USER_GUIDE.md](USER_GUIDE.md)
- **How to contribute?** → See [CONTRIBUTING.md](CONTRIBUTING.md)

## 📁 Project Structure

```
attendance-system/
│
├── main.py                          # Application entry point
│
├── database/
│   ├── __init__.py
│   ├── database.py                  # Database layer (SQLite, CRUD operations)
│   └── attendance.db                # SQLite database (auto-created)
│
├── gui/
│   ├── __init__.py
│   ├── login.py                     # Login window and main application
│   ├── dashboard.py                 # Dashboard view
│   ├── members.py                   # Member management interface
│   ├── attendance.py                # Attendance marking interface
│   ├── reports.py                   # Reports and analytics
│   └── settings.py                  # Settings and administration
│
├── backups/                         # Database backups directory
├── exports/                         # Export files directory
│
├── requirements.txt                 # Python dependencies
├── setup.py                         # Package setup file
├── README.md                        # This file
├── INSTALLATION.md                  # Installation guide
├── USER_GUIDE.md                    # User manual
├── CONTRIBUTING.md                  # Contributing guidelines
├── LICENSE                          # MIT License
└── .gitignore                       # Git ignore file
```

## 🛠️ Technologies Used

| Technology | Purpose | Version |
|-----------|---------|---------|
| Python | Programming Language | 3.8+ |
| Tkinter | GUI Framework | Included |
| SQLite | Database | 3.x |
| Bcrypt | Password Hashing | Latest |
| Pandas | Data Analysis | Latest |
| Matplotlib | Data Visualization | Latest |
| OpenPyXL | Excel Support | Latest |
| ReportLab | PDF Generation | Latest |

## 🔒 Security Features

- **Password Hashing**: Bcrypt algorithm for secure password storage
- **Input Validation**: All user inputs are validated
- **SQL Injection Prevention**: Parameterized queries throughout
- **Access Control**: Role-based permissions (Admin/Staff)
- **Session Management**: Secure login/logout functionality
- **Data Integrity**: SQLite constraints and validation

## 📝 Database Schema

### Users Table
```sql
users (
    user_id INTEGER PRIMARY KEY,
    username TEXT UNIQUE,
    password TEXT (bcrypt hash),
    role TEXT
)
```

### Members Table
```sql
members (
    id INTEGER PRIMARY KEY,
    member_id TEXT UNIQUE,
    full_name TEXT,
    gender TEXT,
    department TEXT,
    email TEXT,
    phone TEXT,
    date_registered TEXT
)
```

### Attendance Table
```sql
attendance (
    attendance_id INTEGER PRIMARY KEY,
    member_id TEXT,
    full_name TEXT,
    department TEXT,
    status TEXT,
    attendance_date TEXT,
    attendance_time TEXT
)
```

## 🆘 Troubleshooting

### Common Issues

**Issue**: `ModuleNotFoundError: No module named 'tkinter'`
- **Solution**: See [INSTALLATION.md](INSTALLATION.md#troubleshooting)

**Issue**: Cannot connect to database
- **Solution**: Ensure `database/` folder has write permissions

**Issue**: Login fails with correct credentials
- **Solution**: Restart the application and clear browser cache (if using web version)

For more troubleshooting, see [INSTALLATION.md](INSTALLATION.md#troubleshooting)

## 📞 Support & Help

1. **Read the Documentation**: Check [USER_GUIDE.md](USER_GUIDE.md) and [INSTALLATION.md](INSTALLATION.md)
2. **Common Issues**: See troubleshooting section above
3. **Report Bugs**: Create an issue with detailed information
4. **Feature Requests**: Open an issue with your suggestions

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for:
- Bug reporting guidelines
- Feature request process
- Code contribution standards
- Development setup

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## 🎯 Roadmap

### Version 1.0 (Current)
- ✅ Core attendance management
- ✅ Member CRUD operations
- ✅ Login system
- ✅ Basic reporting

### Version 1.1 (Planned)
- 📅 Excel/CSV import functionality
- 📅 PDF report export
- 📅 Email notifications
- 📅 Enhanced analytics

### Version 2.0 (Future)
- 📅 QR code scanning
- 📅 Face recognition
- 📅 Mobile app integration
- 📅 Cloud backup

## 👥 Credits

Developed as a professional attendance management solution for educational institutions and businesses.

## 📧 Contact

For questions or feedback, please contact the development team.

---

**Version**: 1.0  
**Last Updated**: June 2026  
**Status**: Active Development  
**License**: MIT
