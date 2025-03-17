# Next.js Login Template

![Next.js](https://img.shields.io/badge/Next.js-13-blue?logo=next.js)
![React](https://img.shields.io/badge/React-18-blue?logo=react)
![MongoDB](https://img.shields.io/badge/MongoDB-6-green?logo=mongodb)

This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app). It provides a bare-bones template for implementing basic login functionality using **Next.js**, **React**, and **MongoDB**.

---

## Features

- **User Authentication**: Users are created and stored in a MongoDB cluster.
- **Password Security**: Passwords are hashed using `bcrypt` for secure storage.
- **JWT Authentication**: JSON Web Tokens (JWT) are generated upon login and stored in HTTP-only cookies for enhanced security.
- **Middleware Routing**: Middleware is used to redirect users to either `auth` or `unauth` subdomains based on their authentication status.

---

## Prerequisites

Before getting started, ensure you have the following:

1. **MongoDB Cluster**: Create a cluster on [MongoDB Atlas](https://www.mongodb.com/atlas/database) if you don’t already have one.
2. **Environment Variables**: Set up the required environment variables as described below.

---

## Setup

### 1. Environment Variables

Create the following files in the root of your project:

- `.env.local` (for local development)
- `.env.production` (for production)

Add the following variables to these files:

```plaintext
NODE_ENV=development # or "production" for production
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/?retryWrites=true&w=majority&appName=<cluster>
JWT_SECRET=<your-secret-string-for-jwt>

Replace the placeholders (<username>, <password>, <cluster>, <your-secret-string-for-jwt>) with your actual values.
```

### 2. Running the Project

Install dependencies and start the development server:

```bash
npm install
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open http://localhost:3000 in your browser to view the application.

## Usage

**Authentication Flow**

1. Unauthenticated Users:

- If you are not logged in (or lack a valid JWT), you will be automatically redirected to http://localhost:3000/unauth/login.

- To create a new user, navigate to http://localhost:3000/unauth/createuser.

2. Authenticated Users:

- Once logged in, you will be redirected to the auth subdomain based on your authentication status.

3. Custom Landing Page:

- If you wish to create a custom landing page instead of redirecting to unauth/login, modify the middleware file located in the src folder.

## Customization

**Middleware**

The middleware file (src/middleware.js) controls the redirection logic based on authentication status. You can modify this file to:

- Change the default redirect paths.

- Add additional conditions for routing.

**Styling**

This template uses basic CSS for styling. You can integrate a CSS framework (e.g., Tailwind CSS, Bootstrap) or use a CSS-in-JS solution (e.g., styled-components) for more advanced styling.

**Contributing**

If you’d like to contribute to this project, feel free to open an issue or submit a pull request. Contributions are welcome!
