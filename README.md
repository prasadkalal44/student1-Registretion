# JWT Authentication Demo

A simple full-stack **JWT Authentication Demo** built with **React** and **Express.js**. This project demonstrates how **JSON Web Tokens (JWT)** are used to authenticate users and protect API routes.

---

# Features

- User Login
- JWT Token Generation
- Protected API Route
- Authentication Middleware
- Token Verification
- Logout Functionality
- Error Handling
- React Frontend with Fetch API
- Express REST API

---

# Tech Stack

## Frontend

- React
- Vite
- CSS
- Fetch API

## Backend

- Node.js
- Express.js
- JSON Web Token (jsonwebtoken)
- CORS

---

# Project Structure

```
jwt-auth-demo/
│
├── backend/
│   ├── index.js
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│   └── package.json
│
└── README.md
```

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/yourusername/jwt-auth-demo.git
```

```bash
cd jwt-auth-demo
```

---

# Backend Setup

Navigate to the backend folder.

```bash
cd backend
```

Install dependencies.

```bash
npm install
```

Start the server.

```bash
node index.js
```

The backend runs at:

```
http://localhost:5000
```

---

# Frontend Setup

Open a new terminal.

```bash
cd frontend
```

Install dependencies.

```bash
npm install
```

Start the React development server.

```bash
npm run dev
```

The frontend runs at:

```
http://localhost:5173
```

---

# Backend Dependencies

Install the required packages:

```bash
npm install express cors jsonwebtoken
```

---

# Demo Login Credentials

Use the following credentials to log in:

| Username | Password |
|----------|----------|
| alice | 1234 |

---

# REST API Endpoints

## Login

Authenticate a user and receive a JWT.

```
POST /login
```

### Request Body

```json
{
  "username": "alice",
  "password": "1234"
}
```

### Successful Response

```json
{
  "token": "eyJhbGciOiJIUzI1NiIs..."
}
```

### Error Response

```json
{
  "message": "Invalid username or password"
}
```

---

## Protected Profile

Returns user information only when a valid JWT is provided.

```
GET /profile
```

### Request Header

```
Authorization: Bearer <JWT_TOKEN>
```

### Successful Response

```json
{
  "message": "Welcome back, alice!"
}
```

### Error Response

```json
{
  "message": "No token provided"
}
```

or

```json
{
  "message": "Invalid or expired token"
}
```

---

# Authentication Flow

1. User enters username and password.
2. React sends a POST request to `/login`.
3. Express validates the credentials.
4. Server generates a JWT.
5. JWT is returned to the frontend.
6. React stores the token in state.
7. React includes the token in the `Authorization` header for protected requests.
8. Express verifies the JWT using middleware.
9. If valid, access to the protected route is granted.

---

# Project Workflow

```
User Login
     │
     ▼
POST /login
     │
     ▼
Validate Credentials
     │
     ▼
Generate JWT
     │
     ▼
Return Token
     │
     ▼
Store Token in React
     │
     ▼
GET /profile
Authorization: Bearer Token
     │
     ▼
JWT Middleware
     │
     ▼
Token Verified
     │
     ▼
Protected Response
```

---

# JWT Payload Example

```json
{
  "username": "alice",
  "iat": 1710000000,
  "exp": 1710003600
}
```

---

# Frontend Functionality

The React application allows users to:

- Log in using demo credentials
- Receive a JWT from the server
- Store the JWT in application state
- Access a protected API endpoint
- Display the protected response
- Log out by clearing the stored token
- Display authentication errors

---

# HTTP Status Codes

| Status Code | Description |
|-------------|-------------|
| 200 | Request Successful |
| 401 | Unauthorized |
| 403 | Forbidden (Invalid or Expired Token) |

---

# Security Notes

This project is intended for learning purposes.

In a production application:

- Store the JWT secret in environment variables.
- Use HTTPS for all API communication.
- Store tokens securely (prefer HttpOnly cookies).
- Hash passwords using **bcrypt**.
- Connect to a real database (e.g., MySQL, PostgreSQL, MongoDB).
- Implement refresh tokens and token expiration handling.

---

# Future Improvements

- User Registration
- Password Hashing (bcrypt)
- Refresh Tokens
- Role-Based Authorization
- Database Integration
- Token Refresh Mechanism
- User Profile Management
- Protected Dashboard
- Persistent Login
- Docker Support

---

# Example API Testing (Postman)

### Login

```
POST http://localhost:5000/login
```

Body

```json
{
  "username": "alice",
  "password": "1234"
}
```

---

### Access Protected Route

```
GET http://localhost:5000/profile
```

Header

```
Authorization: Bearer YOUR_JWT_TOKEN
```

---

# License

This project is provided for educational purposes and can be modified or extended for learning JWT authentication with React and Express.js.

---

# Author

**Prasad kalal**

Built using **React, Express.js, and JSON Web Tokens (JWT)** to demonstrate secure user authentication and protected REST API endpoints.
