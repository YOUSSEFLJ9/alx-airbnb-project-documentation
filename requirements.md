# Airbnb Clone Backend Requirements

This document describes the **technical** and **functional** requirements for the core backend features of the Airbnb Clone project.  
It covers **User Authentication**, **Property Management**, and **Booking System**.

---

## 1. User Authentication

### Functional Requirements
- Users must be able to **register**, **login**, and **logout**.
- Passwords must be stored securely using hashing.
- Authentication tokens (JWT) must be used for session management.
- Roles: `guest`, `host`, and `admin`.

### API Endpoints
- `POST /api/auth/register` → Register a new user  
- `POST /api/auth/login` → Authenticate and return JWT token  
- `POST /api/auth/logout` → Invalidate token (optional server-side store)  
- `GET /api/users/:id` → Get user profile  

### Input / Output
**Register**
```json
Request:
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "strongpassword",
  "role": "guest"
}

Response:
{
  "id": "uuid",
  "name": "John Doe",
  "email": "john@example.com",
  "role": "guest",
  "created_at": "2025-08-30T10:00:00Z"
}
