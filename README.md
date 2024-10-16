Basic JWT Authentication with MongoDB

Overview

This project implements a basic JWT authentication system using Node.js, Express, and MongoDB. It includes public and private routes, where the private route is accessible only with a valid JWT token. The user ID is stored in MongoDB when generating the token.


Technologies Used
Node.js
Express
MongoDB (via Mongoose)
JSON Web Token (JWT)
dotenv (for environment variables)
CORS
Setup Instructions
Prerequisites
Node.js installed
MongoDB installed and running (or access to a MongoDB Atlas cluster)

Step 1: Clone the Repository

Step 2: Install Dependencies

Step 3: Create Environment Variables
Create a .env file in the root of your project with the following content:

JWT_SECRET=your_jwt_secret

MONGODB_URI=mongodb+srv://dhokmangesh678:mangesh123@privateclu.lrpgd.mongodb.net/?retryWrites=true&w=majority&appName=privateClu

Step 4: Start the Server


API Endpoints

1. Generate Token and Store UserId
Endpoint: POST /api/generate-token
Request Body:  { "userId": "12345"}

Response:{   "token": "your_jwt_token"}

2. Access Public Route
Endpoint: GET /api/public
Response:{   "message": "This is a public route"}

3. Access Private Route
Endpoint: GET /api/private
Headers:  Authorization:  your_generated_token

If successfully added the authorization generated token
Response:{
    "message": "This is a private route",
    "userId": "12345"}

Testing the Functionality
Generate a Token:

Use Postman or a similar tool to send a POST request to http://localhost:5000/api/generate-token with a body containing a userId.
Verify that a JWT token is returned.
Access Public Route:

Send a GET request to http://localhost:5000/api/public.
Confirm that you receive a response indicating it's a public route.
Access Private Route:

Send a GET request to http://localhost:5000/api/private with the Authorization header set to Bearer your_generated_token.
Ensure that you receive a response containing the message and the userId.
Check MongoDB:

Open your MongoDB client and verify that the userId has been stored in the specified database.
Conclusion
This project demonstrates a simple JWT authentication system with public and private routes. You can expand upon this foundation to include user registration, roles, or additional features as needed.

