# WMR Trucking

A PHP-based delivery request and tracking web application for WMR Trucking Services.

## Overview

WMR Trucking lets clients register, log in, submit delivery requests, and contact the company. The project also includes an admin dashboard for managing delivery requests, inquiries, and clients.

## Key Features

- User registration and login
- Delivery request submission with pickup and delivery details
- Contact form for customer inquiries
- Admin dashboard for request and status management
- Database-backed storage using MySQL / MariaDB
- PHP server-side logic and HTML/CSS frontend

## Project Structure

- `src/`
  - `html/`: Static landing pages and marketing pages
  - `css/`: Stylesheets for user and admin views
  - `js/`: Frontend JavaScript and client-side behavior
  - `php/`: User-facing PHP pages
    - `index.php`: Main home page
    - `login.php`: Login page
    - `signUp.php`: Registration page
    - `request.php`: Delivery request form
    - `profile.php`: User profile management
    - `handle_contact.php`: Contact form backend
    - `logout.php`: Logout handling
    - `admin/`: Admin dashboard pages
- `wmr_db (7).sql`: Database dump containing schema, stored procedures, and sample data

## Requirements

- PHP 8.x or later
- MySQL / MariaDB
- Web server (Apache, Nginx, or local server stack like XAMPP/WAMP/MAMP)

## Setup Instructions

1. Place the project folder in your web server root.
   - Example for XAMPP: `C:\xampp\htdocs\WMR`
2. Import the database dump into MySQL/MariaDB.
   - Use phpMyAdmin or command line:
     ```sql
     CREATE DATABASE wmr_db CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
     USE wmr_db;
     SOURCE "wmr_db (7).sql";
     ```
3. Configure database credentials if needed.
   - Default credentials are set to `root` with no password.
   - The main PHP connection files use:
     - host: `localhost`
     - database: `wmr_db`
     - username: `root`
     - password: ``
4. Open the application in your browser.
   - Example URL: `http://localhost/WMR/src/php/index.php`

## Usage

- Register a new user with `signUp.php`.
- Log in using `login.php`.
- Submit a delivery request through `request.php`.
- Send messages to the company via the contact form on the home page.
- Admin users are redirected to `src/php/admin/index.php` when logging in as `admin`.

## Database Notes

The database contains these main tables:

- `users`
- `delivery_requests`
- `delivery_status`
- `delivery_status_log`
- `contact_messages`

It also includes a stored procedure:

- `insert_delivery_request`

## Additional Notes

- Google sign-in buttons are present in `login.php` and `signUp.php`, but the OAuth client ID is currently a placeholder (`YOUR_GOOGLE_CLIENT_ID`).
- Make sure the web server has write/read access to the `uploads/` directory if profile pictures are used.
- The project currently assumes the default local database setup, so update connection settings if your environment differs.

## License

This repository does not include an explicit license. Add one if you want to share or publish the project publicly.
