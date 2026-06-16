# User Guide - Attendance Tracking System

## Table of Contents

1. [Getting Started](#getting-started)
2. [Login](#login)
3. [Dashboard](#dashboard)
4. [Members Management](#members-management)
5. [Attendance Marking](#attendance-marking)
6. [Reports & Analytics](#reports--analytics)
7. [Settings](#settings)
8. [Tips & Best Practices](#tips--best-practices)

---

## Getting Started

### System Launch

1. Open a terminal or command prompt
2. Navigate to the project folder
3. Activate the virtual environment (if not already active)
4. Run: `python main.py`
5. The Login window should appear

---

## Login

### Default Admin Account

When the application starts for the first time, a default admin account is created:

- **Username**: `admin`
- **Password**: `admin123`

### Login Process

1. Enter your **Username**
2. Enter your **Password**
3. Click **Login**

### Password Management

**Show Password:**
- Check the "Show password" checkbox to reveal the password as you type

**Forgot Password:**
1. Click the **Forgot Password** button
2. Enter your username
3. Your password will be reset to `password123`
4. Log in with the reset password and change it in **Settings**

---

## Dashboard

The Dashboard is your main view after login. It displays:

### Key Information

| Metric | Description |
|--------|-------------|
| **Total** | Total registered members in the system |
| **Present** | Members marked present today |
| **Absent** | Members marked absent today |

### Recent Attendance

A table showing the last 30 attendance records with:
- Member ID
- Member Name
- Attendance Status
- Date
- Time

### Auto-Update

Dashboard information updates automatically when you perform attendance operations.

---

## Members Management

### Add a New Member

1. Click **Members** in the sidebar
2. Fill in the form fields:

| Field | Required | Rules |
|-------|----------|-------|
| **ID Number** | ✓ | Must be unique, no spaces recommended |
| **Full Name** | ✓ | Enter complete name |
| **Gender** | ✗ | Select from dropdown (Male/Female/Other) |
| **Department** | ✓ | Enter department or class name |
| **Email** | ✗ | Must be valid format (name@domain.com) |
| **Phone** | ✗ | 7-15 characters, can include +, -, spaces |

3. Click **Add**
4. Confirmation message appears

### Update a Member

1. Click **Members**
2. Click a row in the table to select a member
3. Form fields auto-populate with member data
4. Modify the desired fields
5. Click **Update**
6. Confirm the changes

### Delete a Member

1. Click **Members**
2. Click a row in the table to select a member
3. Click **Delete**
4. Confirm the deletion
5. Member is removed from the system

### View All Members

1. Click **Members**
2. Click **View All** to see the complete list

### Search Members

1. Click **Members**
2. Enter search criteria (ID, name, or department)
3. Click **Search**
4. Matching results are displayed
5. Click **View All** to reset the search

---

## Attendance Marking

### Mark Attendance

1. Click **Attendance** in the sidebar
2. Select **Member ID** from the dropdown (search by typing)
3. Select **Status** from dropdown:
   - **Present** - Member attended
   - **Absent** - Member didn't attend
   - **Late** - Member arrived late
   - **Excused** - Member excused from attendance

4. Click **Mark Attendance**
5. Confirmation message appears

### Important Rules

- **One attendance per member per day**: Once marked, you cannot mark the same member again on the same day
- **Automatic timestamp**: Time is recorded automatically
- **Status cannot be changed**: Delete the record and create a new one if correction needed

### Today's Attendance View

The table shows all attendance records for today with:
- Member ID
- Member Name
- Department
- Status
- Time marked

### Prevention of Duplicates

The system prevents accidental duplicate attendance marking for the same member on the same day.

---

## Reports & Analytics

### Today's Attendance Chart

1. Click **Reports** in the sidebar
2. Click **Show Today Pie Chart**
3. A pie chart displays:
   - **Present**: Percentage of members marked present
   - **Absent**: Percentage of members marked absent
   - **Other**: Remaining (not marked yet)

### Chart Information

- Chart is generated from today's attendance records
- Updates dynamically based on current data
- Helps visualize attendance trends quickly

### Future Enhancements

The following report features can be added:
- Weekly attendance summary
- Monthly attendance trends
- Department-wise comparison
- PDF export with detailed statistics
- Email reports

---

## Settings

### Create New User

1. Click **Settings** in the sidebar
2. Under "New Username" section:
   - Enter **New Username**
   - Enter **Password**
   - Select **Role** (Admin/Staff)
   - Click **Create User**

3. Confirmation message appears
4. New user can now log in

### Change Password

1. Click **Settings**
2. Under "Change Password" section:
   - Enter **Username** of the account to change
   - Enter **New Password**
   - Click **Change Password**

3. Password is updated
4. User must log in again with the new password

### Backup Database

1. Click **Settings**
2. Click **Backup Database**
3. Select a folder where backup will be saved
4. Database is backed up with timestamp filename
5. Confirmation message shows backup location

### Import Backup

To restore a backup:
1. Stop the application
2. Navigate to `database/attendance.db`
3. Replace with backup file (or restore from backup folder)
4. Restart the application

---

## Tips & Best Practices

### Best Practices

1. **Change Default Password**: Always change the default admin password on first login
2. **Create User Accounts**: Use the Settings module to create accounts for different staff members
3. **Regular Backups**: Create backups weekly to prevent data loss
4. **Unique Member IDs**: Use consistent ID format (e.g., EMP001, STU001)
5. **Verify Email/Phone**: Ensure contact information is correct when adding members

### Common Tasks

**Mark attendance for multiple members quickly:**
1. Go to Attendance tab
2. Select member and status
3. Mark attendance
4. Repeat for next member (dropdown stays open)

**Find a specific member:**
1. Go to Members tab
2. Type ID or name in the search box
3. Click Search
4. Click on the result to select

**Export Attendance Records:**
- Currently available through database backup
- CSV/PDF export features can be added later

### Navigation Tips

- **Sidebar buttons**: Click to navigate between different modules
- **Treeview tables**: Click a row to select and populate form
- **Search boxes**: Clear by clicking View All or Search buttons
- **Status bar**: Shows current date/time on dashboard

### Data Integrity

- All changes are immediately saved to the database
- SQLite ensures data consistency
- Passwords are securely hashed with bcrypt
- No manual database editing recommended

---

## Troubleshooting User Issues

### Issue: Cannot add member with same ID twice

**Reason**: Member IDs must be unique
**Solution**: Use a different ID or edit existing member

### Issue: "Already marked today" error

**Reason**: Attendance already recorded for this member today
**Solution**: Check today's attendance table or edit existing record

### Issue: Form fields don't clear after adding member

**Solution**: Click **Clear** button to reset form fields

### Issue: Search returns no results

**Solution**: 
- Check spelling
- Use partial names or IDs
- Click **View All** to see all members

### Issue: Cannot log in after password change

**Solution**: 
- Ensure Caps Lock is off
- Use the correct username with the new password
- Try "Forgot Password" to reset

---

## Support & Feedback

For issues or feature requests:
1. Check the [INSTALLATION.md](INSTALLATION.md) for technical troubleshooting
2. Review [README.md](README.md) for project information
3. Check the database/logs for detailed error information

---

**Last Updated**: June 2026  
**Version**: 1.0  
**Support**: Contact system administrator
