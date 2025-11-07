# 🔐 Authentication System Overview

This project implements a full authentication flow using **React Router v6.4+** on the client side and **JWT (JSON Web Token)** on the backend with **Express.js**.

---

## Client-Side Authentication Logic

### Token Handling
- After successful login or signup, the backend returns a **JWT token**.
- The token is saved in `localStorage` together with an expiration timestamp:
  - `token` — stores the JWT string.
  - `expiration` — stores ISO date one hour ahead of the current time.
- The helper functions in `util/auth.js`:
  - `getAuthToken()` — reads the token from storage and checks expiration.
  - `getTokenDuration()` — calculates how long the token remains valid.
  - `tokenLoader()` — makes the token available through React Router’s data API.
  - `checkAuthLoader()` — protects routes (redirects to `/auth` if not logged in).

### Automatic Logout
- In `RootLayout`, a `useEffect` hook monitors the token’s remaining duration.
- When the token expires, it automatically triggers a `POST` request to `/logout`.
- Logout removes both `token` and `expiration` from localStorage and redirects to the home page.

### Protected Routes
- Routes like `/events/new` and `/events/:id/edit` use the `checkAuthLoader` to ensure only authenticated users can access them.
- The delete and edit actions for events include the `Authorization: Bearer <token>` header.

### UI State Based on Token
- `useRouteLoaderData("root")` reads the token across the app.
- The navigation bar dynamically switches:
  - Shows **“Authentication”** when no token is present.
  - Shows **“Logout”** and **restricted links** when a token is active.

---

## Server-Side Authentication Logic

### Token Creation & Validation
- The backend uses **jsonwebtoken** to create and verify tokens.
- `createJSONToken(email)` generates a token valid for 1 hour.
- `checkAuth` middleware validates the `Authorization` header (`Bearer <token>`) and rejects unauthorized requests.

### Signup and Login
- `/signup`: validates email/password and stores new users in the database.
- `/login`: verifies credentials using bcrypt, issues a signed JWT token on success.
- Both routes return `{ token: <JWT> }` in JSON.

### Middleware Protection
- Protected routes (like `/events`) require a valid token.
- The backend checks the `Authorization` header for every non-OPTIONS request.

---

## Core Hooks and APIs Used
- `useRouteLoaderData()` — read token value from root loader.
- `useSubmit()` — programmatic form submission for auto logout.
- `localStorage` — persist authentication state between reloads.
- `redirect()` — from React Router actions/loaders for navigation control.

---
