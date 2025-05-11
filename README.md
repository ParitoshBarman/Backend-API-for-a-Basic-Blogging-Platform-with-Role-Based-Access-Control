# Blogging Platform API

A simple blogging backend platform built using Node.js, Express.js, and MongoDB with role-based access control.

## 🚀 Features

- User Authentication with JWT (Login/Register)
- Role-based Access Control (Admin, Author, User)
- Blog Post CRUD operations
- Middleware: Logger, Authenticator, Role Authorizer
- MongoDB Integration using Mongoose
- Secure Routes based on User Role
- Logger that writes logs to `logs.txt`

## 📦 Tech Stack

- Node.js
- Express.js
- MongoDB + Mongoose
- JSON Web Tokens (JWT)
- bcryptjs for password hashing

## 🧑‍💻 Installation

```bash
git clone <repo-url>
cd project-folder
npm install
```

## 🏁 Running the Server

```bash
node index.js
```

The server runs on **http://localhost:3000**

## 🛠 API Routes

### Root

- `GET /` → Welcome message

### Authentication

- `POST /auth/register` → Register user
- `POST /auth/login` → Login and get JWT token

### Blog Posts

- `POST /posts` → Create blog post (author/admin only)
- `GET /posts` → Get all posts (public)
- `GET /posts/:id` → Get post by ID (public)
- `PATCH /posts/:id` → Update post (author/admin only)
- `DELETE /posts/:id` → Delete post (admin only)

### Authors (Planned)

- `POST /authors` → Add author
- `GET /authors` → List all authors
- `GET /posts/author/:name` → Posts by author name

## 🔐 Roles

- `user`: Can read posts only
- `author`: Can create and update their own posts
- `admin`: Can manage all posts and users

## 🧪 Middleware

- **Logger** → Logs method, URL, and time to `logs.txt`
- **JWT Auth** → Secures protected routes
- **Role Middleware** → Restricts actions by user role

## 📂 Project Structure

```
.
├── controller/
│   ├── authController.js
│   └── blogPostController.js
├── middleware/
│   ├── authMiddleware.js
│   ├── roleMiddleware.js
│   └── loggerMiddleware.js
├── models/
│   ├── blogPostModel.js
│   └── userModel.js
├── routes/
│   ├── authRoutes.js
│   └── blogPostRoutes.js
├── config/
│   └── db.js
├── logs.txt
├── index.js
└── README.md
```

## 📌 Note

- Don't forget to add the `.env` file and configure MongoDB connection string and JWT secret.
