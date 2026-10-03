# Authentication App

A full-stack authentication and authorization application built with **Spring Boot** and **React + TypeScript**.

The project demonstrates secure user authentication using JWT access and refresh tokens, refresh-token rotation, role-based access control, OAuth 2.0 login with Google and GitHub, Redis, and MySQL.

## Project Structure

```text
Authentication-App/
├── backend/
│   ├── src/
│   ├── pom.xml
│   └── ...
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
│
└── README.md
```

## Backend

The backend is developed using Java and Spring Boot.

### Technologies

* Java
* Spring Boot
* Spring Security
* Spring Data JPA
* Hibernate
* MySQL
* Redis
* JWT
* OAuth 2.0
* Maven
* OpenAPI / Swagger
* JUnit

### Backend Features

* User registration and login
* JWT-based authentication
* Access token and refresh token
* Refresh-token rotation
* HTTP-only refresh-token cookie
* Role-Based Access Control (RBAC)
* Google OAuth 2.0 login
* GitHub OAuth 2.0 login
* Redis-based token blacklist on logout
* Redis caching
* Password hashing using BCrypt
* Stateless Spring Security configuration
* Centralized exception handling
* REST APIs
* OpenAPI documentation

## Frontend

The frontend is developed using React and TypeScript.

### Technologies

* React
* TypeScript
* Vite
* React Router
* Axios
* Zustand
* shadcn/ui
* Lucide React
* Framer Motion

### Frontend Features

* Login and registration
* Google and GitHub OAuth login
* Protected routes
* Authentication state management
* Automatic access-token handling
* Refresh-token handling when the access token expires
* Axios interceptor for authenticated API requests
* User dashboard
* User profile
* Responsive authentication UI

## Authentication Flow

### Email and Password Login

```text
User
  ↓
Login
  ↓
Backend
  ↓
Validate credentials
  ↓
Generate Access Token + Refresh Token
  ↓
Refresh Token stored in HTTP-only cookie
  ↓
Access Token used for authenticated API requests
```

### Access Token Expiration

When the access token expires:

```text
Frontend
   ↓
API request
   ↓
Access Token expired
   ↓
Refresh Token sent to backend
   ↓
Backend validates refresh token
   ↓
New Access Token generated
   ↓
Frontend continues authenticated requests
```

The application also implements refresh-token rotation.

### OAuth 2.0 Login

The application supports OAuth login using:

* Google
* GitHub

The OAuth provider authenticates the user first. The backend then retrieves the user's information, creates or updates the corresponding application user, and generates the application's own authentication tokens.

## Security

The application uses several Spring Security features:

* BCrypt password hashing
* JWT authentication
* HTTP-only refresh-token cookie
* Stateless authentication
* Role-based authorization
* Refresh-token rotation
* JWT blacklist using Redis during logout
* OAuth 2.0 authentication

## Database

The application uses **MySQL** for persistent application data.

Redis is used for caching and token-related operations.

## Running the Project

### Backend

Navigate to the backend directory:

```bash
cd backend
```

Run the Spring Boot application using Maven:

```bash
./mvnw spring-boot:run
```

On Windows:

```cmd
mvnw.cmd spring-boot:run
```

Configure your database, Redis, JWT secret, and OAuth credentials in the application's configuration/environment variables before running the application.

### Frontend

Navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

## Environment Configuration

The backend requires configuration for items such as:

* MySQL database
* Redis
* JWT secret
* OAuth 2.0 Google credentials
* OAuth 2.0 GitHub credentials
* Frontend redirect URL

Do not commit real secrets, passwords, OAuth client secrets, or JWT secrets to the repository.

## Repository History

This repository combines the previously separate backend and frontend repositories into a single project while preserving their Git histories.

The backend and frontend remain organized in separate directories:

```text
backend/
frontend/
```

## Author

**Ankit Anand**

GitHub: [Ankit-coder7870](https://github.com/Ankit-coder7870)
# Authentication-App