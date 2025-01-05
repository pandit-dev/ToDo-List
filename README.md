# To-Do List API

This document provides instructions on how to run the To-Do List API project. The project is a RESTful API for managing tasks with user authentication.

## Prerequisites

Before running this project, ensure you have the following installed on your machine:

- **Node.js** (v14 or higher)
- **MongoDB** (local or MongoDB Atlas)
- **Git**

## Installation and Setup

### 1. Clone the Repository

Use Git to clone the repository from GitHub:

```bash
git clone https://github.com/pandit-dev/ToDo-List.git
cd ToDo-List
```

### 2. Install Dependencies

Navigate to the project directory and install the required dependencies using npm:

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory of the project and add the following environment variables:

```env
PORT=4000
MONGO_URI=<Your MongoDB URI>
JWT_SECRET=<Your JWT Secret Key>
```

- **PORT**: The port number on which the server will run.
- **MONGO_URI**: The connection string for your MongoDB database.
- **JWT_SECRET**: A secret key for signing JWT tokens.

### 4. Start the Server

Run the following command to start the server:

```bash
npm start
```

The server will start on `http://localhost:4000` (or the port specified in your `.env` file).

## Running the Application

### Testing the Endpoints

You can test the API endpoints using a tool like Postman or cURL. Below are some example requests:

#### User Registration

**Endpoint:** `POST /api/users/register`

**Request Body:**
```json
{
  "username": "testuser",
  "password": "testpassword"
}
```

#### User Login

**Endpoint:** `POST /api/users/login`

**Request Body:**
```json
{
  "username": "testuser",
  "password": "testpassword"
}
```

**Response:**
```json
{
  "_id": "someUserId",
  "username": "testuser",
  "token": "your_jwt_token"
}
```

#### Accessing Protected Routes

After logging in, use the token in the `Authorization` header to access protected routes:

**Header:**
```bash
Authorization: Bearer your_jwt_token
```

### Example Protected Route

**Endpoint:** `POST /api/tasks`

**Request Body:**
```json
{
  "title": "New Task",
  "description": "Task description"
}
```

## Conclusion

By following these steps, you should be able to run the To-Do List API locally and test its endpoints. Ensure all required environment variables are correctly set in the `.env` file and that MongoDB is running.

