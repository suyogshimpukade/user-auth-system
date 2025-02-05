User Authentication System

This is a Node.js-based user authentication system that includes registration, login, password reset, and authentication using JWT (JSON Web Token). The project uses MongoDB for data storage and Nodemailer for email-based password reset functionality.

Technologies Used

Node.js

Express.js

MongoDB (Mongoose)

JSON Web Token (JWT)

Bcrypt.js (Password Hashing)

Nodemailer (Email Service)

dotenv (Environment Variables)

Postman (API Testing)

Project Setup

Prerequisites

Ensure you have the following installed:

Node.js

MongoDB

Postman (for API testing)

Installation

Clone the repository:

git clone https://github.com/your-repository/user-auth-system.git
cd user-auth-system

Install dependencies:

npm install

Set up environment variables:
Create a .env file in the root directory and add the following:

PORT=5000
MONGODB_URI=mongodb://localhost:27017/user_auth
JWT_SECRET=your_secret_key
JWT_EXPIRES_IN=1h
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password

Start the server:

nodemon server.js

The server should now be running at http://localhost:5000.

API Endpoints

User Authentication Routes

Register a new user

POST /api/auth/register

Request Body:

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}

Login user

POST /api/auth/login

Request Body:

{
  "email": "john@example.com",
  "password": "password123"
}

Forgot Password

POST /api/auth/forgot-password

Request Body:

{
  "email": "john@example.com"
}

Reset Password

POST /api/auth/reset-password/:token

Request Body:

{
  "password": "newpassword123"
}

Troubleshooting

If you get a 500 Internal Server Error, check your .env configurations and ensure MongoDB is running.

If password reset emails are not working, make sure you have enabled less secure apps for your email or use an SMTP service.

Use console.log() statements to debug server responses in authController.js.