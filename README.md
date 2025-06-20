
# 🧑‍💼 User Management API

This document describes the available routes for managing users, including registration, login, OTP verification, and password reset.

---

## 🌐 Base URL

```
http://yourdomain.com/api/user
```

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
```

**Success Response:**
```json
{
  "message": "Registration successful",
  "user": {
    "id": "123",
    "email": "john@example.com",
    "name": "John Doe"
  }
}
```

---

### 🔐 GET `/login`

**Description:** Login an existing user.

**Query Parameters:**
```
/login?email=john@example.com&password=password123
```

**Success Response:**
```json
{
  "message": "Login successful",
  "token": "jwt_token_here"
}
```

---

### 👤 GET `/read-user`

**Description:** Fetch logged-in user info.

**Headers:**
```
Authorization: Bearer <jwt_token>
```

**Success Response:**
```json
{
  "user": {
    "id": "123",
    "email": "john@example.com",
    "name": "John Doe"
  }
}
```

---

### 🚪 GET `/logOut`

**Description:** Logout the currently logged-in user.

**Headers:**
```
Authorization: Bearer <jwt_token>
```

**Success Response:**
```json
{
  "message": "Logout successful"
}
```

---

### 📩 GET `/verify-email/:email`

**Description:** Check if email exists and send OTP for verification.

**Example URL:**
```
/verify-email/john@example.com
```

**Success Response:**
```json
{
  "message": "OTP sent to email"
}
```

---

### 🔢 GET `/verify-OTP/:email/:otp`

**Description:** Verify OTP sent to user's email.

**Example URL:**
```
/verify-OTP/john@example.com/123456
```

**Success Response:**
```json
{
  "message": "OTP verified successfully"
}
```

---

### 🔁 GET `/reset-password/:email/:otp`

**Description:** Verify OTP before allowing password reset.

**Example URL:**
```
/reset-password/john@example.com/123456
```

**Success Response:**
```json
{
  "message": "OTP verified. You can now reset your password."
}
```

---

## 🔐 Authentication Notes

- Routes like `/read-user` and `/logOut` require a valid JWT token.
- Use the `Authorization` header:
```
Authorization: Bearer <jwt_token>
```

---

## 📬 Contact

Call : 01722924089   Email : mdenamulh1998@gmail.com   
