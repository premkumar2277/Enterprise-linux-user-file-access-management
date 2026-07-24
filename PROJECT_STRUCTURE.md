
# Project Structure

## Enterprise Directory Layout

```text
/enterprise
│
├── backups
│   ├── daily_backup.tar.gz
│   ├── weekly_backup.tar.gz
│   └── monthly_backup.tar.gz
│
├── departments
│   ├── engineering
│   │   ├── app.py
│   │   ├── deploy.sh
│   │   ├── Dockerfile
│   │   ├── README.md
│   │   └── requirements.txt
│   │
│   ├── finance
│   │   ├── budget_2026.xlsx
│   │   ├── expenses.xlsx
│   │   ├── invoices.csv
│   │   └── tax_report.pdf
│   │
│   ├── human_resources
│   │   ├── employee_records.csv
│   │   ├── leave_requests.txt
│   │   ├── payroll.xlsx
│   │   └── policies.pdf
│   │
│   ├── it_support
│   │   ├── backup.sh
│   │   ├── inventory.csv
│   │   ├── server_list.txt
│   │   └── tickets.log
│   │
│   └── sales
│       ├── customers.csv
│       ├── monthly_sales.xlsx
│       ├── quotations.pdf
│       └── targets.txt
│
├── logs
│   ├── access.log
│   ├── backup.log
│   ├── security.log
│   └── system.log
│
├── reports
│   ├── permission_report.txt
│   ├── storage_report.txt
│   ├── system_summary.txt
│   └── user_report.txt
│
├── scripts
│
└── shared
    ├── announcements.txt
    ├── company_handbook.pdf
    ├── holiday_list.pdf
    ├── meeting_notes.txt
    └── project_plan.docx
```

---

# Directory Description

## backups/

Stores system backup archives.

Examples:

- Daily Backup
- Weekly Backup
- Monthly Backup

---

## departments/

Contains separate directories for each department.

Each department has:

- Dedicated owner
- Department group
- Restricted permissions

Departments:

- Engineering
- Finance
- Human Resources
- IT Support
- Sales

---

## logs/

Stores application and system log files.

Examples:

- Access Logs
- Security Logs
- Backup Logs
- System Logs

---

## reports/

Contains generated administrative reports.

Examples:

- User Reports
- Permission Reports
- Storage Reports
- System Summary

---

## shared/

A collaborative directory accessible to authorized users.

Features:

- Shared Group
- SGID Enabled
- Group Collaboration

---

# Security Design

Each department has:

- Separate directory
- Separate owner
- Separate group
- Secure Linux permissions

Shared resources are managed through the **company_shared** group.

---

# Project Highlights

- Enterprise Folder Structure
- Department Isolation
- Shared Collaboration
- Secure Access Control
- Linux Administration Best Practices
