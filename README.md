# Ikigai: Clinic Appointment Management System

Ikigai (I-CARE) is a full-stack MERN web application designed to streamline and centralize clinic operations. It replaces traditional manual processes for appointment scheduling, doctor management, and patient records with a comprehensive, role-based digital platform.

This system was developed as a project for a Software Engineering course, demonstrating a complete software development lifecycle, from requirements gathering and system design to implementation, testing, and deployment.

## Core Features

The application is divided into three distinct portals based on user roles:

### Admin Portal

  * **Dashboard:** View system statistics, including total doctors and pending approval requests.
  * **Doctor Management:** Manage all doctor profiles (update details, remove accounts).
  * **Approve Requests:** Review and approve or reject new registration requests from doctors.
  * **Shift Management:** Assign and manage doctor shifts to ensure clinic coverage.

### Doctor Portal

  * **Dashboard:** See an overview of scheduled appointments, completed appointments, and pending feedback.
  * **Appointment Management:** View and filter all upcoming, past, and current appointments. Update appointment status (e.g., "Completed") and add medical notes.
  * **Shift Schedule:** View all assigned shifts in a clear calendar or list format.
  * **Feedback Review:** Read and manage patient feedback for completed consultations.
  * **Profile Management:** Update personal details, credentials, specialty, and consultation fees.

### Patient Portal

  * **Authentication:** Securely register for a new account or log in.
  * **Dashboard:** View summaries of upcoming and past appointments.
  * **Find Doctors:** Search and filter all available doctors by specialty.
  * **Appointment Booking:** Schedule new appointments with a chosen doctor, and cancel or reschedule existing ones.
  * **Payment:** View consultation fees and handle payments (UI implemented).
  * **Feedback:** Submit feedback and a rating for completed appointments.
  * **Profile Management:** Update personal profile and medical history.

## Technology Stack

The project is built on the MERN stack (MongoDB, Express.js, React.js, Node.js) and follows a Model-View-Controller (MVC) architecture.

### Frontend

  * **Framework:** React.js (built with Vite)
  * **Routing:** React Router (`react-router-dom`)
  * **UI/Styling:** Tailwind CSS, Ant Design (`antd`), Lucide Icons
  * **State Management:** React Context API (`AuthContext.jsx`)
  * **API Client:** Axios
  * **Date/Time:** `dayjs`

### Backend

  * **Framework:** Node.js / Express.js
  * **Database:** MongoDB (with Mongoose ODM)
  * **Authentication:** JSON Web Tokens (JWT) & `bcryptjs` for password hashing
  * **Middleware:** `cors` (Cross-Origin Resource Sharing), `morgan` (logging), `multer` (file uploads)

## System Architecture

The application uses a **Model-View-Controller (MVC)** design to ensure a clean separation of concerns.

  * **Model:** Handled by Mongoose schemas (e.g., `User.js`, `Appointment.js`, `Shift.js`) in the `backend/models` directory, defining the data structure.
  * **View:** Handled by the **React.js** frontend, which renders the UI and interacts with the API.
  * **Controller:** Handled by **Express.js** in the `backend/controllers` directory, which processes all business logic, handles API requests, and interacts with the database models.

### Deployment Diagram

### Component Diagram

## Testing

The project includes a suite of tests to ensure quality and reliability:

  * **Backend (White Box):** Unit tests for controllers were written using **Jest**. Test files are located in `backend/controllers/__tests__`.
  * **Frontend (Black Box):** End-to-end user flow tests (e.g., login, appointment booking, admin approvals) were conducted using **Cypress**. Test files are in `frontend/cypress/e2e`.

## Project Structure

The repository is organized into three main folders: `frontend`, `backend`, and `documentations`.

```
Ikigai-Clinic-Appointment-Management-System/
│
├── backend/
│   ├── config/         # Database connection (db.js)
│   ├── controllers/    # Business logic for routes
│   ├── middlewares/    # Auth, error handling, file uploads (multer)
│   ├── models/         # Mongoose schemas (User, Appointment, etc.)
│   ├── routes/         # API endpoint definitions (admin, doctor, patient)
│   ├── setup/          # (Schema setup scripts)
│   ├── uploads/        # (Default storage for uploaded files)
│   ├── utils/          # Email utilities, validators
│   ├── app.js          # Express app configuration
│   └── server.js       # Server entry point
│
├── frontend/
│   ├── public/         # Static assets
│   ├── src/
│   │   ├── assets/     # Images, fonts, styles
│   │   ├── components/ # Reusable UI components (Admin, Doctor, Patient)
│   │   ├── context/    # Global state (AuthContext)
│   │   ├── hooks/      # Custom hooks (useAuth)
│   │   ├── pages/      # Top-level page components (Admin, Doctor, Patient, Auth)
│   │   ├── routes/     # React Router setup (index.jsx)
│   │   └── services/   # API client configuration
│   ├── cypress/        # E2E tests
│   ├── index.html      # HTML entry point
│   ├── package.json    # Frontend dependencies
│   └── vite.config.js  # Vite configuration
│
└── documentations/
    ├── 22i-0751_22i-0798_22i-01285_SE_final_report.pdf
    ├── Software Project Plan.pdf
    ├── System Architecture.pdf
    └── SE Project Presentation.pptx
```

## Getting Started

### Prerequisites

  * Node.js (v18 or later recommended)
  * MongoDB (a local instance or a cloud-hosted connection string)

### Backend Setup

1.  Navigate to the `backend` directory:
    ```sh
    cd backend
    ```
2.  Install the required dependencies:
    ```sh
    npm install
    ```
3.  Create a `.env` file in the `backend` root directory.
4.  Add your MongoDB connection string and a JWT secret to the `.env` file:
    ```env
    MONGO_URI=your_mongodb_connection_string
    JWT_SECRET=your_secret_key
    ```
5.  Start the backend server (uses `nodemon` for auto-restarting):
    ```sh
    npm run dev
    ```
    The server will be running on the port specified in your `server.js` (e.g., `http://localhost:5000`).

### Frontend Setup

1.  Open a new terminal and navigate to the `frontend` directory:
    ```sh
    cd frontend
    ```
2.  Install the required dependencies:
    ```sh
    npm install
    ```
3.  Create a `.env` file in the `frontend` root directory.
4.  Add the URL of your running backend server:
    ```env
    VITE_API_URL=http://localhost:5000
    ```
5.  Start the frontend development server:
    ```sh
    npm run dev
    ```
    The React application will be available at `http://localhost:5173`.

## Project Team

  * Mavra Mehak - 22I-0798
  * Maryum Tanvir - 22I-0751
  * Salman Khan - 22I-1285
