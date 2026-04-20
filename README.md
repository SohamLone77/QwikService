# UrbanClapClone

## Project Overview
UrbanClapPro is a web application that aggregates home utility services such as beauty, electrical maintenance, home cleaning, and pest control. Users can browse services, book appointments at convenient times, and manage their bookings in one place.

The system includes an Angular frontend, a Go backend API, and a MySQL database. The backend seeds initial data on startup.

## Features
- Browse a list of services
- Register, log in, and manage a profile
- Book services with date and time selection
- View and cancel bookings
- Service images and pricing

## Tech Stack
- Frontend: Angular
- Backend: Go
- Database: MySQL (GORM)

## Prerequisites
- Node.js LTS
- Go (1.20+ recommended)
- MySQL 8+

## Folder Structure
- client: Angular frontend
- server: Go API server
- db: SQL schema and seed data
- doc_assets: screenshots

## Configuration
Update the MySQL credentials in server/config/config.go:

```go
Username: "root"
Password: "123456"
Name:     "urbanClap"
```

## Database Setup
1. Ensure MySQL is running.
2. Create the database:

```sql
CREATE DATABASE urbanClap;
```

The backend auto-migrates tables and seeds data on startup.

## Run Backend
1. Ensure MySQL is installed and running.
2. Create a database named "urbanClap".
3. Update the MySQL credentials in server/config/config.go.
4. Start the server:

```bash
cd server
go run .
```

The API runs on http://localhost:3000.

## Run Frontend
1. Install Node.js LTS.
2. Install dependencies:

```bash
cd client
npm install
```

3. Start the dev server:

```bash
npm start
```

The UI runs on http://localhost:4200.

## API Endpoints (Common)
- GET /api/getServices
- POST /api/bookService
- GET /api/getBookings/{custId}

## Troubleshooting
- If the backend fails with "sql: database is closed", verify MySQL is running and credentials are correct.
- If Angular cannot find services, ensure the backend is running and the API base URL is correct.
- If "go" is not recognized, restart the terminal to refresh PATH.

## Useful Scripts
Frontend (client/package.json):
- npm start: run dev server
- npm test: run unit tests
- npm run e2e: run end-to-end tests
