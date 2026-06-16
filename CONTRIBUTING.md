# Contributing to Attendance System

Thank you for your interest in contributing to the Attendance Tracking System! This document provides guidelines for contributing.

## Code of Conduct

- Be respectful and professional
- Provide constructive feedback
- Help other contributors
- Report issues responsibly

## How to Contribute

### 1. Report Bugs

Found a bug? Please report it by:

1. Checking if the issue already exists
2. Creating a new issue with:
   - Clear title
   - Detailed description
   - Steps to reproduce
   - Expected vs. actual behavior
   - Screenshots (if applicable)
   - Python version and OS

### 2. Suggest Features

Have a feature idea? Please:

1. Check existing issues first
2. Describe the feature clearly
3. Explain the use case and benefits
4. Provide examples if possible

### 3. Submit Code Changes

#### Setup Development Environment

```bash
git clone <repository-url>
cd attendance-system
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

#### Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b bugfix/your-bug-fix
```

#### Make Your Changes

- Follow PEP 8 style guide
- Write clear, descriptive commit messages
- Add comments for complex logic
- Test your changes thoroughly

#### Commit and Push

```bash
git add .
git commit -m "Brief description of changes"
git push origin feature/your-feature-name
```

#### Create a Pull Request

1. Push your branch to the repository
2. Create a Pull Request with:
   - Clear title
   - Description of changes
   - Reference to related issues
   - Screenshots/demos (if applicable)

### 4. Improve Documentation

Documentation improvements are always welcome:

- Fix typos
- Clarify instructions
- Add examples
- Improve organization

## Contribution Guidelines

### Code Quality

- Write clean, readable code
- Use meaningful variable/function names
- Add docstrings to functions
- Remove debug code and comments
- Follow existing code style

### Testing

Before submitting:

1. Test the application fully
2. Check for regressions
3. Verify error handling
4. Test edge cases

### Commit Messages

Use clear, conventional commit messages:

```
feat: Add QR code scanning feature
fix: Resolve duplicate attendance marking bug
docs: Update installation guide
refactor: Simplify member search logic
test: Add unit tests for attendance marking
```

## Project Structure

```
attendance-system/
├── main.py                 # Application entry point
├── database/
│   ├── __init__.py
│   └── database.py        # Database layer (CRUD operations)
├── gui/
│   ├── __init__.py
│   ├── login.py           # Login and main app window
│   ├── dashboard.py       # Dashboard view
│   ├── members.py         # Members management
│   ├── attendance.py      # Attendance marking
│   ├── reports.py         # Reports and analytics
│   └── settings.py        # Settings and administration
├── requirements.txt       # Python dependencies
├── README.md             # Project overview
├── INSTALLATION.md       # Installation instructions
├── USER_GUIDE.md        # User documentation
├── CONTRIBUTING.md      # This file
└── LICENSE              # MIT License
```

## Areas for Contribution

### High Priority

- [ ] CSV/Excel import functionality
- [ ] PDF export with reports
- [ ] Email notifications
- [ ] Automated backup scheduler
- [ ] Enhanced search and filtering

### Medium Priority

- [ ] Dark mode / Light mode toggle
- [ ] QR code attendance scanning
- [ ] Barcode support
- [ ] Weekly/monthly report generation
- [ ] Department-wise analytics

### Nice to Have

- [ ] Face recognition attendance
- [ ] Multi-language support
- [ ] SMS notifications
- [ ] Mobile app integration
- [ ] Cloud backup support

## Questions?

- Check the documentation first
- Review existing issues and discussions
- Create a new issue with your question

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing! Your efforts help make this project better. 🎉
