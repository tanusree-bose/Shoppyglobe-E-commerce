# ShoppyglobeE-commerce

## Project Overview

**Shoppyglobe** is a Node.js-based e-commerce backend API built with Express and MongoDB. It provides essential features for handling products, managing shopping carts, and authenticating users. This API supports operations like fetching product data, managing a shopping cart, user authentication using JWT, and handling errors effectively.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API Routes](#api-routes)
- [MongoDB Setup](#mongodb-setup)
- [Authentication & Authorization](#authentication-authorization)
- [Testing](#testing-with-thunderclient)
- [Error Handling & Validation](#error-handling-validation)
- [Contributions](#contributions)

---

## Features

🛍️ **User Authentication**:  
- User registration and login with JWT authentication.

📦 **Product Management**:  
- CRUD operations for products (Create, Read, Update, Delete).

🛒 **Shopping Cart**:  
- Add, update, and remove products in the cart.

🔐 **JWT Authentication & Authorization**:  
- Secure API with JWT token-based access for protected routes (like cart operations).

💾 **MongoDB Integration**:  
- Store and manage product and cart data in MongoDB.

⚠️ **Error Handling & Validation**:  
- Ensures proper validation of inputs and robust error handling.

---

## Installation

### Step 1: Clone the Repository
```bash
git clone 

cd Shoppyglobe_Backend_project


2. **Install Dependencies**:

    npm install

3. **Environment Variables**: Create a .env file in the root directory and add your MongoDB connection string:

    MongoDB_URL = "mongodb://localhost:27017/shoppyGlobe"
    Jwt_secret_key = "MySecretKey123"
    PORT = 5000

4. ### Run the Application:

    npm start

5. ### The API should be running on http://localhost:5000.

## Usage

The API has various endpoints that can be used to interact with the application. Ensure to obtain a JWT token by registering or logging in to access protected routes.


## Node.js and Express API with MongoDB Integration
This project demonstrates how to set up a Node.js application using Express and MongoDB for handling products and a shopping cart. The API supports operations such as fetching product data, managing a shopping cart, user authentication, and error handling.

## Features

Product Management: Fetch and manipulate product data.

Shopping Cart: Add, update, and remove products in the cart.

User Authentication: JWT-based authentication for secure access to the cart.

MongoDB Integration: Store and manage product and cart data in MongoDB.

API Error Handling & Validation: Ensure robustness and input validation.

Table of Contents

## Installation
API Routes
MongoDB Setup
Authentication & Authorization
Testing
Error Handling & Validation
Contributions
Installation
Prerequisites
Node.js (v14 or higher)
MongoDB (or a MongoDB cloud instance like MongoDB Atlas)

### Step 1: Clone the repository

bash
Copy code
git clone 
cd node-express-mongodb-api

### Step 2: Install dependencies
bash
Copy code
npm install

### Step 3: Set up environment variables
Create a .env file at the root of the project and add the following environment variables:

makefile
Copy code
PORT=5000
MONGODB_URI=mongodb://localhost:27017/your-database-name
JWT_SECRET=your-jwt-secret-key

### Step 4: Start the server
bash
Copy code
npm start
This will start the application on http://localhost:5000.


## MongoDB Setup

### Collections:  

- 🛍️ **Products**:  
  Each product contains the following fields:  
  - `name`: Product name (String)  
  - `price`: Price of the product (Number)  
  - `description`: Product description (String)  
  - `stock`: Available stock quantity (Number)  

- 🛒 **Cart**:  
  Stores items added to the shopping cart with the following fields:  
  - `productId`: Reference to the product (ObjectId)  
  - `quantity`: Quantity of the product in the cart (Number)  

### MongoDB Database Schema Example:

- **Products Collection**:  
  ```json
  {
    "_id": ObjectId("12345"),
    "name": "Product A",
    "price": 12.12,
    "description": "A great product.",
    "stock": 100
  }

Cart Collection:
json
Copy code
{
  "_id": ObjectId("67890"),
  "productId": ObjectId("12345"),
  "quantity": 2
}
## Authentication & Authorization

JWT Authentication
The API uses JWT (JSON Web Token) for authenticating users. After logging in via the /login endpoint, users will receive a token that must be included in the Authorization header as a Bearer token when accessing protected routes (like the cart).

Protecting Cart Routes:
All cart-related routes (POST /cart, PUT /cart/:id, DELETE /cart/:id) require the user to be authenticated. If no valid JWT is provided, a 401 Unauthorized response will be returned.

## Testing with ThunderClient

### Testing Steps:  

1. 🔥 **Install ThunderClient**  
   Install **ThunderClient** (a popular API testing extension for VSCode).  

2. 📝 **Create a New Request**  
   Create a new request for each of the API routes listed above.  

3. 🔄 **Choose the Correct HTTP Method**  
   Use the appropriate HTTP method (GET, POST, PUT, DELETE) for each route.  

4. 📑 **Add the Request Body**  
   For POST and PUT requests, make sure to add the necessary request body in the request.  

5. 🔒 **Include the JWT Token for Protected Routes**  
   For protected routes (such as cart-related operations), include the **JWT token** in the Authorization header as a **Bearer token**.  


