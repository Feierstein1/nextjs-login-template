Next.js Login Template
This is a Next.js project bootstrapped with create-next-app. It provides a bare-bones template for implementing basic login functionality using Next.js, React, and MongoDB.

-Features
User Authentication: Users are created and stored in a MongoDB cluster.

Password Security: Passwords are hashed using bcrypt for secure storage.

JWT Authentication: JSON Web Tokens (JWT) are generated upon login and stored in HTTP-only cookies for enhanced security.

Middleware Routing: Middleware is used to redirect users to either auth or unauth subdomains based on their authentication status.

-Prerequisites
Before getting started, ensure you have the following:

MongoDB Cluster: Create a cluster on MongoDB Atlas if you don’t already have one.

Environment Variables: Set up the required environment variables as described below.

- Setup

1. Environment Variables
   Create the following files in the root of your project:

.env.local (for local development)

.env.production (for production)

Add the following variables to these files:
NODE_ENV=development # or "production" for production
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/?retryWrites=true&w=majority&appName=<cluster>
JWT_SECRET=<your-secret-string-for-jwt>

Replace the placeholders (<username>, <password>, <cluster>, <your-secret-string-for-jwt>) with your actual values.

- Usage
  Authentication Flow
  Unauthenticated Users:

If you are not logged in (or lack a valid JWT), you will be automatically redirected to http://localhost:3000/unauth/login.

To create a new user, navigate to http://localhost:3000/unauth/createuser.

Authenticated Users:

Once logged in, you will be redirected to the auth subdomain based on your authentication status.

Custom Landing Page:

If you wish to create a custom landing page instead of redirecting to unauth/login, modify the middleware file located in the src folder.

-Best Practices
Security:

Ensure your JWT_SECRET is a strong, random string.

Never expose sensitive environment variables (e.g., MONGO_URI, JWT_SECRET) in client-side code.

Performance:

Use Incremental Static Regeneration (ISR) or Server-Side Rendering (SSR) for dynamic content.

Optimize images and assets for faster load times.

Scalability:

Consider using a CDN for static assets.

Use a connection pooling library (e.g., mongoose) for efficient database connections.

-Troubleshooting
Connection Issues:

Ensure your MongoDB cluster allows connections from your IP address.

Double-check your MONGO_URI for typos or incorrect credentials.

Environment Variables:

Restart the development server after modifying .env files.

Ensure .env files are not committed to version control (add them to .gitignore).

-Contributing
If you’d like to contribute to this project, feel free to open an issue or submit a pull request. Contributions are welcome!
