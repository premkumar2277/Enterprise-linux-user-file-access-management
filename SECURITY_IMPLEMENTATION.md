
# Security Implementation

## Overview

Security is a critical part of Linux system administration. This project implements user authentication, group-based access control, file ownership, Linux permissions, and SGID to simulate a secure enterprise environment.

---

# Security Objectives

- Protect department data
- Restrict unauthorized access
- Allow secure collaboration
- Implement least privilege principle
- Follow Linux security best practices

---

# User Security

Each department has its own dedicated user account.

| User | Department |
|------|------------|
| admin | Administration |
| hr_admin | Human Resources |
| finance_admin | Finance |
| developer1 | Engineering |
| developer2 | Engineering |
| sales_exec | Sales |
| support_eng | IT Support |
| intern | Internship |

Benefits:

- Individual accountability
- Secure authentication
- Department isolation

---

# Group Security

Each department has its own Linux group.

| Group | Purpose |
|--------|---------|
| admins | Administration |
| hr | Human Resources |
| finance | Finance |
| developers | Engineering |
| sales | Sales |
| support | IT Support |
| interns | Internship |
| company_shared | Shared Collaboration |

Benefits:

- Simplified permission management
- Secure access control
- Easier administration

---

# File Ownership

Ownership was configured using:

```bash
chown
```

Example:

```bash
chown -R hr_admin:hr /enterprise/departments/human_resources
```

Each department owns its own files.

Benefits:

- Better security
- Easier auditing
- Controlled access

---

# Linux Permissions

Permissions were configured using:

```bash
chmod
```

Examples:

```bash
chmod -R 770 /enterprise/departments/human_resources
chmod -R 775 /enterprise/shared
```

Permission Meaning:

| Permission | Description |
|------------|-------------|
| 770 | Owner & Group have full access |
| 775 | Owner & Group full access, Others read & execute |

---

# SGID Implementation

SGID was enabled using:

```bash
chmod g+s /enterprise/shared
```

Purpose:

- New files inherit the directory group.
- Improves collaboration.
- Prevents incorrect group ownership.

Verification:

```bash
ls -ld /enterprise/shared
```

Example Output:

```text
drwxrwsr-x
```

The **s** indicates SGID is enabled.

---

# Access Control

The project enforces:

- Department isolation
- Controlled collaboration
- Secure shared directory
- Group-based access

Example:

- HR users cannot modify Finance files.
- Developers cannot access HR confidential data.
- Shared resources are available only to the authorized shared group.

---

# Security Best Practices

Implemented:

- Principle of Least Privilege
- Group-Based Access Control
- Separate Department Ownership
- Secure Directory Permissions
- Shared Collaboration Group
- SGID for Team Collaboration

---

# Validation

Security was validated by:

- Switching users using `su`
- Testing file creation
- Verifying group ownership
- Confirming permission restrictions
- Testing shared directory access

---

# Learning Outcomes

This project provided hands-on experience with:

- Linux User Security
- Linux Group Security
- File Ownership
- Linux Permissions
- SGID
- Enterprise Access Control
- Linux Security Best Practices

---

# Conclusion

This project demonstrates how Linux security features can be combined to create a secure, scalable, and manageable enterprise file system suitable for Linux Administration, DevOps, and Cloud environments.
