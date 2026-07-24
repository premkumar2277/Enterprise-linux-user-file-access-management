
# Testing and Validation

## Overview

Testing and validation ensure that the Linux Enterprise User, File & Access Management System functions correctly. This document describes the tests performed to verify user management, group membership, permissions, ownership, and access control.

---

# Test Environment

| Item | Value |
|------|-------|
| Operating System | Red Hat Enterprise Linux 9 |
| Shell | Bash |
| Project Directory | /enterprise |
| User Privileges | Root & Standard Users |

---

# Test 1 - Verify Directory Structure

### Command

```bash
tree /enterprise
```

### Expected Result

- All directories are created successfully.
- Department folders exist.
- Logs, Reports, Scripts, Shared, and Backups directories exist.

**Status:** ✅ Passed

---

# Test 2 - Verify Users

### Command

```bash
cat /etc/passwd | grep -E "admin|developer|finance|sales|support|intern"
```

### Expected Result

All project users are listed.

**Status:** ✅ Passed

---

# Test 3 - Verify Groups

### Command

```bash
cat /etc/group | grep -E "admins|developers|finance|sales|support|company_shared|interns|hr"
```

### Expected Result

All project groups are displayed.

**Status:** ✅ Passed

---

# Test 4 - Verify Ownership

### Command

```bash
ls -lR /enterprise
```

### Expected Result

Each department directory is owned by the correct user and group.

Example:

- hr_admin : hr
- finance_admin : finance
- developer1 : developers
- sales_exec : sales
- support_eng : support

**Status:** ✅ Passed

---

# Test 5 - Verify Permissions

### Command

```bash
ls -ld /enterprise/departments/*
```

### Expected Result

Permissions display:

```text
drwxrws---
drwxrwsr-x
```

SGID should be visible where configured.

**Status:** ✅ Passed

---

# Test 6 - Verify SGID

### Command

```bash
ls -ld /enterprise/shared
```

### Expected Result

```text
drwxrwsr-x
```

The **s** indicates SGID is enabled.

**Status:** ✅ Passed

---

# Test 7 - User Access Test

### Login as Developer

```bash
su - developer1
```

### Create File

```bash
touch /enterprise/shared/project_notes.txt
```

### Verify

```bash
ls -l /enterprise/shared
```

Expected Result:

- File created successfully.
- Group ownership inherited from company_shared.

**Status:** ✅ Passed

---

# Test 8 - Access Restriction

### Login

```bash
su - hr_admin
```

### Attempt

```bash
cd /enterprise/departments/finance
```

### Expected Result

Permission denied (if permissions restrict access).

**Status:** ✅ Passed

---

# Test 9 - Disk Usage

### Command

```bash
du -sh /enterprise
```

### Expected Result

Displays total storage used by the project.

**Status:** ✅ Passed

---

# Test 10 - File Search

### Command

```bash
find /enterprise -type f
```

### Expected Result

Lists all project files.

**Status:** ✅ Passed

---

# Validation Checklist

| Test | Status |
|------|--------|
| Directory Structure | ✅ Passed |
| Users Created | ✅ Passed |
| Groups Created | ✅ Passed |
| Ownership Configured | ✅ Passed |
| Permissions Applied | ✅ Passed |
| SGID Enabled | ✅ Passed |
| Shared Directory Tested | ✅ Passed |
| Access Control Verified | ✅ Passed |
| File Search Verified | ✅ Passed |
| Disk Usage Verified | ✅ Passed |

---

# Conclusion

All project components were successfully tested and validated. The system demonstrates proper Linux administration practices, including secure user management, permission handling, SGID configuration, and enterprise-style access control.

This project is suitable as a learning portfolio for Linux Administration, DevOps, and Multi-Cloud engineering.
