# 🧑‍💼 User Management API

This document describes the available routes for managing users, including registration, login, OTP verification, and password reset.

---

## 🌐 Base URL

Replace `yourdomain.com` with your actual server domain or `localhost:PORT`.

---

## 📌 API Endpoints

### ➕ POST `/register`

**Description:** Register a new user.

**Request Body (JSON):**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
