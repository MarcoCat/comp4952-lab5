
# Patient Management System - Setup Guide

## Prerequisites

1. **Download and Install MySQL:**
   - Download from [MySQL](https://dev.mysql.com/downloads/mysql/).
   - During installation, set the root password and remember it for later.

2. **Download and Install Node.js:**
   - Download from [Node.js](https://nodejs.org/).

3. **Install `http-server` globally (for serving client-side files):**
   ```bash
   npm install -g http-server
   ```

## Setup Instructions

1. **Clone or Download the Project Files**

   Ensure you have the project folders (`server1` for the client and `server2` for the API server).

2. **MySQL Setup**

   - Open the MySQL command-line client:
     ```bash
     mysql -u root -p
     ```
   - Enter your root password and then create the `patients_db` database:
     ```sql
     CREATE DATABASE patients_db;
     EXIT;
     ```
   - In the `server2/db.js` file, replace the following with your MySQL credentials:
     - **User:** Replace `'root'`.
     - **Password:** Replace `'password'` with your MySQL root password.

3. **Install Node.js Dependencies**

   In both `server1` and `server2` folders, run:
   ```bash
   npm install
   ```

## Running the Application

### 1. **Start the Client (server1)**

   Navigate to the `server1` directory and start the client:
   ```bash
   cd path/to/server1
   http-server -c-1
   ```

   The client will be available at `http://localhost:8080`.

### 2. **Start the API Server (server2)**

   Navigate to the `server2` directory and start the server:
   ```bash
   cd path/to/server2
   Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process  # (Only needed on Windows)
   node server.js
   ```

   The API server will be running at `http://localhost:3000`.

## Using the Application

- **Insert Sample Patient Data:**
  - Open your browser and go to `http://localhost:8080`.
  - Click "Insert Sample Patient Data" to add predefined patients to the database.
  
- **Run SQL Queries:**
  - Enter SQL queries (either `SELECT` or `INSERT`) in the textarea and click "Submit Query" to run them against the database.

## Troubleshooting

- Ensure that MySQL is running before starting the server.
- If you encounter PowerShell execution policy issues on Windows, use:
  ```bash
  Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
  ```

## Notes

- Modify the MySQL credentials in `server2/db.js` as per your system setup (username, password, database).
- Use the predefined queries or create your own `SELECT` and `INSERT` statements.
