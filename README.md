# SAP Leave Management System

<p align="center">
  <img src="https://img.shields.io/badge/SAP-Leave%20Management%20System-0D76A8?style=for-the-badge&logo=sap&logoColor=white" alt="SAP Leave Management System" />
</p>

<p align="center">
  <a href="#overview"><img src="https://img.shields.io/badge/Status-Interview%20Ready-28a745?style=flat-square" alt="Status" /></a>
  <a href="#tech-stack"><img src="https://img.shields.io/badge/Tech-Stack-0078D4?style=flat-square" alt="Tech Stack" /></a>
  <a href="#architecture"><img src="https://img.shields.io/badge/Architecture-ABAP%20%2B%20React-ff6b6b?style=flat-square" alt="Architecture" /></a>
</p>

A backend-focused employee leave management system built around SAP ABAP Cloud and OData services, with a React frontend prototype for demonstration and user interaction.

This project is designed to streamline employee leave workflows including application, validation, approval/rejection, leave balance validation, and leave history tracking.

## Overview

The system automates the end-to-end leave management lifecycle:

- Employee can submit leave requests
- System validates leave eligibility and date consistency
- Manager reviews and approves or rejects requests
- Approved requests reduce leave balance safely
- Rejected requests remain non-impacting
- Leave history is available for reporting and audit purposes

## Tech Stack

<p align="center">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML" />
  <img src="https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS" />
  <img src="https://img.shields.io/badge/ABAP-Cloud-0D76A8?style=for-the-badge&logo=sap&logoColor=white" alt="ABAP Cloud" />
  <img src="https://img.shields.io/badge/CDS-Data%20Model-0D76A8?style=for-the-badge&logo=sap&logoColor=white" alt="CDS" />
  <img src="https://img.shields.io/badge/OData-v4-0D76A8?style=for-the-badge&logo=sap&logoColor=white" alt="OData" />
</p>

### Core Tools & Technologies

- SAP ABAP Cloud
- ABAP programming language
- CDS views / data definitions
- OData V4 service exposure
- React frontend prototype
- JavaScript, HTML, CSS
- SAP Business Application Studio / Eclipse ADT workflow

## Architecture

```text
React Frontend Prototype
        │
        ├── User Interaction
        ├── Leave Request Forms
        └── Manager Dashboard
        │
        ▼
SAP ABAP Cloud Backend
        │
        ├── Custom Database Tables
        ├── Business Logic Classes
        ├── Validation & Approval Rules
        └── OData V4 Service
        │
        ▼
Leave Management Data Layer
```

### Business Logic Flow

```text
Employee
   ↓
Apply Leave
   ↓
Request Validation
   ↓
PENDING Status
   ↓
Manager Approval / Rejection
   ↓
APPROVED / REJECTED
   ↓
Balance Update (Approved Only)
   ↓
Leave History Report
```

## Features

- Employee master management
- Leave type configuration
- Leave balance tracking
- Leave application workflow
- Leave validation checks
- Manager approval and rejection
- Automatic leave deduction on approval
- Duplicate balance update protection
- Leave history reporting
- OData V4 service integration

## Leave Types

| Code | Leave Type |
|------|------------|
| CL | Casual Leave |
| SL | Sick Leave |
| EL | Earned Leave |

## Business Rules

1. Employee must exist before applying for leave.
2. From date cannot be after the To date.
3. Available leave balance is verified before approval.
4. Only valid requests are created with PENDING status.
5. Only PENDING requests can be approved or rejected.
6. Rejected requests do not reduce leave balance.
7. Only APPROVED requests update the employee balance.
8. Duplicate balance deduction is prevented using validation logic.

## Project Structure

```text
sap-leave-management-system/
├── backend/
│   ├── tables/
│   ├── classes/
│   ├── cds/
│   ├── services/
│   └── README.md
├── frontend/
│   └── React frontend prototype
├── docs/
│   └── Project documentation
├── README.md
└── .gitignore
```

## Backend Components

The backend includes modular ABAP objects such as:

- `ZLM_EMPLOYEE`
- `ZLM_LEAVE_TYPE`
- `ZLM_LEAVE_BAL`
- `ZLM_LEAVE_REQ`
- `ZCL_LEAVE_SAMPLE_DATA`
- `ZCL_LEAVE_VALIDATION`
- `ZCL_LEAVE_APPROVAL`
- `ZCL_LEAVE_REJECTION`
- `ZCL_LEAVE_BALANCE_UPDATE`
- `ZCL_LEAVE_REPORT`

## OData Service

Service definition:

- `ZUI_LM_LEAVE`

Service binding:

- `ZUI_LM_LEAVE_O4`

Entity set:

- `LeaveRequests`

## Frontend Prototype

This repository also includes a React-based frontend prototype with mock data that simulates the leave journey and demonstrates the user experience for employees and managers.

### Demo Credentials

| Role | Employee ID | Password |
|------|-------------|----------|
| Employee | EMP001 | employee123 |
| Manager | MGR001 | manager123 |

## Why This Project Stands Out

- SAP-centric enterprise workflow design
- Real business use-case implementation for HR and leave operations
- Strong focus on validation, business logic, and approval processes
- Clean separation between frontend prototype and backend ABAP logic
- Suitable for discussions around enterprise application development and SAP integration

## Interview Highlights

This project demonstrates:

- Enterprise application thinking
- Business rule implementation
- Workflow design and approval-based systems
- Integration between frontend and backend architecture
- SAP ABAP + OData service development concepts
- Practical understanding of HR process automation

## Future Enhancements

- Real SAP backend integration with live OData consumption
- Role-based access enhancements
- Dashboard analytics for leave trends
- Notification workflows for employee and manager actions
- Reporting visuals for monthly and quarterly leave summaries

## License

This project is intended for learning and demonstration purposes.

---

<p align="center">
  <strong>Built for enterprise workflow automation and SAP-based leave process management.</strong>
</p>
