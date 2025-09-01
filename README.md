Full-Stack Authentication Project with CodeIgniter 4 and ReactJS
This project is a complete, full-stack application built to showcase secure user authentication and a simple data dashboard. The backend is a robust API powered by CodeIgniter 4, while the frontend is a dynamic, single-page application developed with ReactJS. Together, they demonstrate how to create a secure, token-based system and manage related data.

Key Features
Token-Based Authentication: The core of this application's security lies in JSON Web Tokens (JWT). After a user successfully logs in, the API issues a token that must be presented with all future requests to protected endpoints. This ensures that only authenticated users can access sensitive data.

Unified Registration: The registration process is streamlined into a single API call. A new user's information is submitted, and the backend handles inserting data into two separate, related tables: one for basic authentication details and another for teacher-specific information.

Secure Data Access: The data retrieval endpoints for both users and teachers are protected by an authentication filter. Any request to these routes without a valid JWT will be rejected, preventing unauthorized access.

Responsive React Frontend: The frontend is a clean and intuitive user interface built with React. It features a login page, a registration page, and two separate data tables for users and teachers. The design uses Tailwind CSS to ensure a modern, responsive layout that looks great on any device.

Getting Started
To get this project running, you'll need to set up both the backend and the frontend.

1. Backend Setup (CodeIgniter)

First, create a new CodeIgniter 4 project using Composer. Once created, navigate to the project root and install the PHP-JWT library, which is essential for token-based authentication.

composer create-project codeigniter4/appstarter my-backend
cd my-backend
composer require firebase/php-jwt

Next, set up your database. Use the provided SQL schema to create the auth_user and teachers tables. Then, configure your database connection and set a secure JWT secret key in your .env file. Place the controller, model, and filter files from this project into their respective directories within your CodeIgniter project.

Finally, start the backend server to get the APIs up and running:

php spark serve

2. Frontend Setup (ReactJS)

The frontend is a single App.jsx file. You can integrate this file into a new or existing React project. A quick way to start is with create-react-app:

npx create-react-app my-frontend
cd my-frontend

Replace the content of the default src/App.jsx with the code provided. The frontend uses Tailwind CSS for styling, so you'll need to set that up according to the official guide. Once everything is in place, you can start the frontend server:

npm start

The frontend will be available in your browser, ready to communicate with your backend APIs.

Project Structure and Communication
The frontend and backend communicate via a set of well-defined API endpoints. The frontend sends user data in a POST request to the /api/register-teacher endpoint, which handles the creation of both a new user and a related teacher record on the backend. For secure data retrieval, it sends a GET request to endpoints like /api/users or /api/teachers, including the JWT in the Authorization header. This token is validated by the AuthFilter on the backend before the request is processed.

This project provides a complete and functional example of a modern web application structure. Feel free to explore and modify the code to fit your specific needs.
