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

NODE_ENV=development # or "production" for production
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/?retryWrites=true&w=majority&appName=<cluster>
JWT_SECRET=<your-secret-string-for-jwt>
