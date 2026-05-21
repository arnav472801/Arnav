# ERH PRO

A modern medical records and patient management application built with React, Vite, and Express.

## Overview

**ERH PRO** provides a clean interface for healthcare staff to manage patients, view patient profiles, and store medical records. The project includes:

- React frontend with Tailwind-style UI and routing
- Express backend with authentication and record API endpoints
- JWT-based login/register flow
- Local persistence for patient data in browser storage
- Simple JSON-based server storage for patients and records

## Key Features

- Secure authentication: login and register via JWT
- Dashboard for quick access to patient management
- Patient directory with search by name or contact
- Add new patients with structured patient details
- Patient profile page for reviewing history
- Add and view medical records for patients

## Tech Stack

- Frontend: React, Vite, React Router, Axios
- Backend: Node.js, Express, dotenv, helmet, cors
- Authentication: JSON Web Tokens (JWT)
- Storage: browser `localStorage` for UI data, server `data/store.json` for records

## Project Structure

- `/client` — React application
- `/server` — Express API server
- `package.json` — project scripts and dev workflow

## Setup and Run Locally

### Prerequisites

- Node.js 18+ installed
- npm available

### Install dependencies

```bash
npm install
npm install --prefix server
npm install --prefix client
```

### Start the app

```bash
npm run dev
```

This command starts both the backend server and the frontend client concurrently.

### Alternatively start individually

```bash
npm run server
npm run client
```

- Frontend: `http://localhost:5173`
- Backend: `http://localhost:5000`

## Backend API Endpoints

- `POST /api/auth/login` - user login
- `POST /api/auth/register` - user registration
- `GET /api/auth/profile` - authenticated user profile
- `GET /api/patients` - list all patients
- `POST /api/patients` - add a patient
- `PUT /api/patients/:id` - update patient details
- `GET /api/records/patient/:patientId` - get records for a patient
- `POST /api/records` - add a medical record

## Configuration

Create a `.env` file in `/server` if needed. Example values:

```env
PORT=5000
NODE_ENV=development
JWT_SECRET=your_jwt_secret_here
```

## Notes

- The frontend currently uses browser local storage for patient and record data in `/client/src/utils/patientStorage.js`.
- The backend stores records in a JSON file at `/server/data/store.json`.
- The app is designed for local development and can be extended with a proper database and production-ready user management.

## Future Improvements

- Add full backend integration for patient CRUD operations
- Implement role-based access control
- Add unit and integration tests
- Replace local storage with a database such as MongoDB or PostgreSQL

## License

This project is provided as-is for learning and development.
