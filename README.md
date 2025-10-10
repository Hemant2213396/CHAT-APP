# ChatApp

Simple realtime chat application with a Node.js/Express + MongoDB backend and a React (Vite) frontend.

## Features
- User authentication (JWT)
- Send/receive messages
- Image upload support (Cloudinary)
- Separated backend (server/) and frontend (client/) folders

## Prerequisites
- Node.js 16+
- npm
- MongoDB (local or hosted URI)
- Cloudinary account (optional, for image uploads)

## Environment variables

Create .env files in each folder with the following keys:

- server/.env
  - MONGODB_URI=<your MongoDB connection string>
  - JWT_SECRET=<your jwt secret>
  - CLOUDINARY_CLOUD_NAME=<cloudinary cloud name> (optional)
  - CLOUDINARY_API_KEY=<cloudinary api key> (optional)
  - CLOUDINARY_API_SECRET=<cloudinary api secret> (optional)
  - PORT=5000 (optional)

- client/.env
  - VITE_BACKEND_URL=http://localhost:5000

Note: The frontend reads VITE_BACKEND_URL (see client/context/AuthContext.jsx). Set it to your backend base URL.

## Installation & Quick start

1. Install and start the backend
   ```bash
   cd server
   npm install
   # add server/.env
   npm run server
   ```
   - Typical server script: starts dev server (nodemon) or node server.js.

2. Install and start the frontend
   ```bash
   cd client
   npm install
   # add client/.env
   npm run dev
   ```
   - Frontend served by Vite (default on http://localhost:5173).

## Available scripts (common)
- server
  - npm run server — start backend in development
  - npm start — (if configured) start production server
- client
  - npm run dev — start Vite dev server
  - npm run build — build production assets
  - npm run preview — preview production build

(Check each package.json in server/ and client/ for exact script names.)

## Project structure (top-level)
- server/ — Express API, models, controllers, middleware
- client/ — React app (Vite), pages, components, contexts
- README.md — this file

## Deployment
- Build the client (npm run build) and serve the static build from a static host or integrate with the server.
- Configure environment variables in your hosting provider (MongoDB URI, JWT secret, Cloudinary keys, backend URL for frontend).

## Notes & troubleshooting
- If CORS errors occur, ensure backend allows requests from the frontend origin.
- Ensure VITE_BACKEND_URL matches the backend base URL including protocol and port.
- Check server logs for MongoDB connection and JWT errors.

## Contributing
- Open an issue or submit a pull request. Keep changes small and focused.

## License
Specify a license or add LICENSE file as needed.
