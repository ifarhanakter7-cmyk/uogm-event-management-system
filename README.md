# UoGMRAK — Event Management System (EMS)

**University of Greater Manchester — RAK Academic Centre**  
**Final Year Undergraduate Project | 2025–2026**

---

## Project Overview

EMS-UoGMRAK is a role-based web application developed to digitise the university event management lifecycle at the RAK Academic Centre.

The system aims to replace the informal, WhatsApp-based event coordination process with a centralised platform that supports event proposals, multi-level approvals, student registration, QR-code attendance tracking, feedback collection, budget tracking and reporting.

It provides different access levels for administrators, event organisers, academic coordinators, internal management, RAKDOK and students.

## Project Objectives

- Digitise and organise the university event management process.
- Provide a structured, multi-level event approval workflow.
- Simplify event registration and attendance tracking.
- Support communication through in-system notifications.
- Enable post-event feedback and reporting.
- Provide centralised event and document management.

## Key Features

- **Role-Based Access Control:** Access for six different user roles.
- **Event Proposal Management:** Organisers can submit and manage event proposals.
- **Multi-Level Approval Workflow:** Event proposals go through Academic Coordinator, Internal Management and RAKDOK approval stages.
- **Student Registration:** Students can browse and register for university events.
- **QR-Code Attendance:** QR-based check-in to support event attendance tracking.
- **Notifications and Reminders:** In-system notifications for relevant event activities.
- **Feedback and Ratings:** Students can provide post-event feedback and star ratings.
- **Budget Tracking:** Budget information can be managed for individual events.
- **Document Management:** Upload and manage event-related documents.
- **Event Gallery:** Manage event images through an approval process.
- **Analytics and Reporting:** Dashboard for event information and reports.
- **Event Archive:** Maintain records of completed events.

## User Roles

The system supports six user roles:

| Role | Main Responsibility |
|---|---|
| Administrator | Overall system administration |
| Event Organiser | Event proposals and event management |
| Academic Coordinator | Academic-level event approval |
| Internal Management | Internal review and approval |
| RAKDOK | Final designated approval stage |
| Student | Event browsing, registration, attendance and feedback |

## Technologies Used

| Component | Technology |
|---|---|
| Frontend | HTML5, CSS3, Bootstrap, JavaScript |
| Backend | PHP 8.x |
| Database | Microsoft SQL Server |
| Authentication | PHP Sessions and Role-Based Access Control |
| Icons | Font Awesome 6 |
| Fonts | Google Fonts — Inter |
| Local Development Environment | XAMPP |
| Database Management | SQL Server Management Studio (SSMS) |

## Project Structure

The main project directory is organised as follows:

```text
EMS_UoGMRAK/
│
├── auth/              # Login, logout, registration and session checks
├── api/               # Backend PHP scripts and application operations
├── pages/             # Application pages and dashboards
├── includes/          # Shared interface components
│
├── assets/
│   ├── css/           # Stylesheets
│   ├── js/            # JavaScript files
│   └── uploads/       # Application upload directory
│
├── config/
│   ├── db.example.php # Example database configuration (if included)
│   └── constants.php  # Application URL and global settings
│
├── database/
│   ├── ems_uogmrak_schema.sql  # Database table definitions
│   └── ems_uogmrak_seed.sql    # Sample database records
│
├── .gitignore
└── README.md
```

The exact contents may vary depending on the version of the project.

## Getting Started

Follow the instructions below to set up the application locally.

### 1. Prerequisites

Install the following software:

1. **XAMPP** — Provides Apache and the PHP development environment.  
   https://www.apachefriends.org/

2. **Microsoft SQL Server Express** — Database server.  
   https://www.microsoft.com/en-us/sql-server/sql-server-downloads

3. **SQL Server Management Studio (SSMS)** — Used to manage the SQL Server database.  
   https://aka.ms/ssmsfullsetup

4. **Web Browser** — Google Chrome, Mozilla Firefox or another modern browser.

5. **Microsoft ODBC Driver for SQL Server and PHP SQLSRV drivers** — Required for PHP to connect to Microsoft SQL Server. Install compatible versions for your PHP environment.

### 2. Place the Project in XAMPP

1. Download or clone this repository.
2. Locate the project folder named `EMS_UoGMRAK`.
3. Copy the folder into the XAMPP `htdocs` directory.

The expected location is:

```text
C:\xampp\htdocs\EMS_UoGMRAK\
```

### 3. Start Apache

1. Open the XAMPP Control Panel.
2. Locate Apache.
3. Click **Start**.
4. Confirm that Apache is running.

### 4. Create the Database

1. Open SQL Server Management Studio.
2. Connect to your local SQL Server instance.
3. Open a new query window.
4. Execute:

```sql
CREATE DATABASE ems_uogmrak;
```

5. Confirm that the database has been created successfully.

### 5. Import the Database Schema

1. In SSMS, open the project file:

```text
database/ems_uogmrak_schema.sql
```

2. Select the `ems_uogmrak` database.
3. Execute the SQL script.
4. Confirm that the database tables have been created.

### 6. Import Sample Data

To populate the system with sample records:

1. Open:

```text
database/ems_uogmrak_seed.sql
```

2. Select the `ems_uogmrak` database.
3. Execute the script.

Only use the sample data after checking that it contains no real student or staff information and that any sample credentials are safe for local testing.

### 7. Configure the Database Connection

1. Locate the example database configuration file, if included:

```text
config/db.example.php
```

2. Make a local copy named `db.php`.
3. Update the database server, database name and authentication settings for your local SQL Server installation.
4. Save the file.

**Security note:** The local `config/db.php` file may contain database credentials. It must not be committed to GitHub. The repository should contain only the example configuration file.

### 8. Configure the Application URL

Open:

```text
config/constants.php
```

Set the application URL to match your local project directory:

```php
define('APP_URL', 'http://localhost/EMS_UoGMRAK');
```

Save the changes.

### 9. Run the Application

1. Ensure Apache is running in XAMPP.
2. Ensure SQL Server is running.
3. Open your web browser.
4. Visit:

```text
http://localhost/EMS_UoGMRAK
```

The EMS-UoGMRAK login page should appear if the local configuration is correct.

## Testing Accounts

The original project includes sample accounts intended to test different user roles.

For security reasons, default passwords and live credentials are not published in this repository. Use only locally configured test accounts and safe sample data.

## Testing and Validation

The project development included testing of the application's main functionality and workflows.

The testing process covered:

- Unit testing
- Integration testing
- System testing
- Role-based access and workflow validation
- Database connectivity and application functionality

## Common Problems and Solutions

| Problem | Suggested Solution |
|---|---|
| Cannot connect to database | Check the local database configuration, SQL Server service and PHP SQLSRV driver installation. |
| Blank white page | Confirm that Apache is running and check the PHP error logs. |
| Images or CSS are not loading | Verify the application URL and project directory configuration. |
| Database tables are missing | Confirm that the schema SQL script was executed against the correct database. |
| Application cannot connect to SQL Server | Check the server instance name and authentication settings. |

## Known Limitations

- The current version is a prototype and has not been deployed to a live server.
- Email and SMS notifications are not integrated; notifications are currently handled within the application.
- A dedicated mobile application is not available in the current version.

## Academic Project Information

This system was developed as an undergraduate final-year academic project at the RAK Academic Centre.

The project was created for academic purposes and is not intended for commercial use or redistribution.

## Author

**Farhana Akter Mim**  
BEng (Hons) Software Engineering  
University of Greater Manchester

---

*This repository documents an undergraduate software engineering project and its development.*
