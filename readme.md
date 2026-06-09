## 🧭 Project Overview

PayFlow is a secure digital wallet and transaction processing backend system inspired by modern fintech platforms. The system supports wallet management, fund transfers, transaction tracking, role-based access control, and transaction safety mechanisms such as daily transfer limits and duplicate transaction prevention. Built with Express.js, TypeScript, MongoDB, and JWT authentication, the platform follows a modular architecture for scalability and maintainability.
---

## 📌 Key Features

### 🔐 Authentication & Authorization

- JWT-based authentication with secure access and refresh token mechanism.
- Role-based access control (Admin, User, Agent).
- Password encryption using bcrypt for secure credential storage.
- Protected APIs using middleware-based authorization.

### 💳 Wallet Management

- Automatic wallet creation during user and agent registration.
- Wallet balance management with real-time updates.
- Fund transfers between users with balance validation.
- Cash-in and cash-out operations supported through agents.
- Admin controls for wallet blocking/unblocking and agent approval.

### 💸 Transaction Processing Engine

- Secure money transfers with unique transaction reference IDs.
- Transaction status tracking (Pending, Success, Failed).
- Complete transaction history and audit trail.
- Daily transaction limits to prevent misuse and suspicious activity.
- Duplicate transaction prevention using idempotency validation.
- Automatic balance updates after successful transactions.

### 📊 Transaction Monitoring

- Detailed transaction logs for traceability and debugging.
- User-wise and agent-wise transaction history retrieval.
- Admin dashboard APIs for monitoring all platform transactions.
- Commission tracking for agents.

### 🏗️ Scalable Backend Architecture

- Modular architecture with separate Authentication, Wallet, User, and Transaction modules.
- RESTful API design following industry best practices.
- MongoDB + Mongoose integration with schema validation.
- TypeScript-based codebase for better maintainability and type safety.

---

## 🧱 Suggested Project Structure

```plaintext
src/
├── modules/
│   ├── auth/
│   ├── user/
│   ├── wallet/
│   └── transaction/
├── middlewares/
├── config/
├── utils/
├── app.ts
```

---

## ⚙️ Tech Stack

| Package                 | Description                                        |
| ----------------------- | -------------------------------------------------- |
| `bcryptjs`              | Library for password hashing                       |
| `cookie-parser`         | Parse Cookie header and populate `req.cookies`     |
| `cors`                  | Middleware to enable CORS                          |
| `dotenv`                | Loads environment variables from `.env`            |
| `express`               | Web framework for Node.js                          |
| `http-status-codes`     | Constants for standard HTTP status codes           |
| `jsonwebtoken`          | JWT creation and verification                      |
| `mongodb`               | Official MongoDB driver for Node.js                |
| `mongoose`              | ODM (Object Data Modeling) library for MongoDB     |
| `passport`              | Authentication middleware                          |
| `passport-local`        | Strategy for username/password authentication      |
| `zod`                   | Schema validation library                          |
| `typescript`            | Typed JavaScript for safer coding                  |
| `ts-node-dev`           | Runs TypeScript files with auto-restart on changes |
| `eslint`                | Linter for maintaining code quality                |
| `typescript-eslint`     | ESLint parser and plugin for TypeScript            |
| `@types/bcryptjs`       | TypeScript types for `bcryptjs`                    |
| `@types/cookie-parser`  | TypeScript types for `cookie-parser`               |
| `@types/cors`           | TypeScript types for `cors`                        |
| `@types/express`        | TypeScript types for `express`                     |
| `@types/jsonwebtoken`   | TypeScript types for `jsonwebtoken`                |
| `@types/passport`       | TypeScript types for `passport`                    |
| `@types/passport-local` | TypeScript types for `passport-local`              |

---

## 📡 API Endpoints

Base URL: `/api/v1`

### 🔐 Auth

| Method | Endpoint            | Description                 |
| ------ | ------------------- | --------------------------- |
| POST   | /auth/login         | Login with email & password |
| POST   | /auth/refresh-token | Refresh JWT token           |

### 👤 User

| Method | Endpoint        | Description                  |
| ------ | --------------- | ---------------------------- |
| POST   | /user/register  | Register a new user or agent |
| GET    | /user/all-users | [Admin] Get all users        |
| GET    | /user/:id       | [Admin] Get user by ID       |
| PATCH  | /user/:id       | [Admin] Change agent status  |

### 🏦 Wallet

| Method | Endpoint            | Description                        |
| ------ | ------------------- | ---------------------------------- |
| GET    | /wallet/all-wallets | [Admin] Get all wallets            |
| GET    | /wallet/:id         | [Admin] Get wallet by ID           |
| PATCH  | /wallet/:id         | [Admin] Update user wallet details |
| POST   | /wallet/withdraw    | Withdraw money from wallet         |
| POST   | /wallet/transfer    | Transfer money to another user     |
| POST   | /wallet/cashIn      | [Agent] Add money to user wallet   |

### 📜 Transactions

| Method | Endpoint                      | Description                        |
| ------ | ----------------------------- | ---------------------------------- |
| GET    | /user-transaction/userId      | [User] Get own transaction history |
| GET    | /transaction/all-transactions | [Admin] Get all transactions       |
| GET    | /transaction/:id              | [Admin] Get transaction by ID      |
| GET    | /agent-commission             | [Agent] Get own commission history |

---

## 🔐 Role-Based Access Control (RBAC)

- **Admin:** Full access to users, agents, wallets, and transactions management.
- **Agent:** Manage cash-in/cash-out operations and view commission history.
- **User:** Perform wallet top-up, withdrawal, transfers, and view personal transaction history.

---

## ⚙️ Configuration

Create a `.env` file in your project root and use the following structure. Make sure to **replace placeholder values** with your actual configuration.

```env
PORT=5000
DATABASE_URL=mongodb://localhost:27017
NODE_ENV=development
BCRYPT_SALT_ROUND=Give a round

# JWT Settings
JWT_ACCESS_SECRET=your_jwt_access_secret
JWT_ACCESS_EXPIRES=your_jwt_access_expires
JWT_REFRESH_SECRET=your_jwt_refresh_secret
JWT_REFRESH_EXPIRES=your_jwt_refresh_expires

# Frontend URL
FRONTEND_URL=your frontend url

# Admin Credentials
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=strongpassword
ADMIN_PHONE=+8801234567890
```

---

## 📥 Installation

Clone the project and install dependencies:

```bash
git clone https://github.com/khaledsaifulla010/DigiPay-Digital-Wallet-System-Backend.git
cd DigiPay-Digital-Wallet-System-Backend
npm install
```

---


