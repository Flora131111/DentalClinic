# Dental Clinic Management System

A web-based dental clinic management system built with PHP and MySQL. Features role-based access for administrators, dentists, and clients with appointment scheduling, messaging, and feedback capabilities.

## Features

### Admin
- Manage all users (CRUD operations)
- View and manage all appointments
- Approve client account requests
- Send messages to all users
- View feedback and ratings

### Dentist
- Manage own client list
- Create and manage appointments
- Dynamic weekly timetable
- Message clients and admin

### Client
- View upcoming and past appointments
- Submit feedback and ratings
- Message dentists and admin

## Tech Stack

- **Backend:** PHP 8.x with MySQLi
- **Database:** MySQL
- **Frontend:** HTML5, CSS3, Bootstrap 5.3.1
- **Animations:** GSAP 3.12.2
- **Icons:** Font Awesome 6.x
- **Fonts:** Google Fonts (Poppins)

## Prerequisites

- PHP 8.x or higher
- MySQL 8.x or higher
- Web browser

### macOS Installation (via Homebrew)

```bash
# Install Homebrew if not installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install PHP and MySQL
brew install php mysql

# Start MySQL service
brew services start mysql
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/DentalClinic.git
cd DentalClinic
```

### 2. Set Up the Database

```bash
# Log into MySQL
mysql -u root

# Create database and import schema
CREATE DATABASE dental_clinic;
exit;

# Import the schema with sample data
mysql -u root dental_clinic < database/schema.sql
```

### 3. Configure Database Connection

The database is configured in `db.php`. Default settings for local development:

```php
$host = 'localhost';
$username = 'root';
$password = '';
$database = 'dental_clinic';
```

### 4. Start the Server

```bash
php -S localhost:8000
```

### 5. Access the Application

Open your browser and navigate to:
- **Home:** http://localhost:8000
- **Login:** http://localhost:8000/login.php

## Test Accounts

| Role | Email | Password |
|------|-------|----------|
| Admin | admin@dental.com | password |
| Dentist | goni@dental.com | password |
| Dentist | gloria@dental.com | password |

## Project Structure

```
DentalClinic/
├── admin/                  # Admin dashboard and pages
│   ├── admin_dashboard.php
│   ├── users.php
│   ├── appointments.php
│   ├── feedback.php
│   ├── messages.php
│   └── view_requests.php
├── client/                 # Client pages
│   ├── client_dashboard.php
│   ├── appointments.php
│   ├── feedback.php
│   └── messages.php
├── dentist/                # Dentist pages
│   ├── dentist_dashboard.php
│   ├── clients.php
│   ├── appointments.php
│   ├── timetable.php
│   └── messages.php
├── database/               # Database schema
│   └── schema.sql
├── style/                  # CSS and JS assets
│   ├── home.css
│   ├── jsClinic.js
│   └── images/
├── PHPMailer-master/       # Email library
├── db.php                  # Database connection
├── check_auth.php          # Authentication middleware
├── index.php               # Landing page
├── login.php               # Login page
├── logout.php              # Logout handler
├── styles.css              # Dashboard styles
└── README.md
```

## Database Schema

### Tables

- **users** - User accounts with role assignments
- **roles** - Role definitions (admin, dentist, client)
- **appointments** - Scheduling with status tracking
- **messages** - Internal messaging system
- **feedback** - Client ratings and comments
- **tokens** - Remember-me authentication tokens
- **client_requests** - Public account requests

## Authentication

- Session-based authentication
- Optional "Remember Me" with persistent tokens
- Role-based access control (role_id: 1=admin, 2=dentist, 3=client)
- Password hashing with `password_hash()` / `password_verify()`

## Color Theme

The application uses a green and white color scheme:
- Primary Green: `#22c55e`
- Dark Green: `#166534`
- Background: `#ffffff`

## License

This project is for educational purposes.
