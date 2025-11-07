# CRUD_NODE

A simple Node.js Express application that provides CRUD (Create, Read, Update, Delete) operations for user management using MongoDB and Mongoose.

## Prerequisites

Before running this application, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (version 14 or higher)
- [MongoDB](https://www.mongodb.com/) (running locally or a MongoDB Atlas account)

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd CRUD_NODE
   ```

2. Install the dependencies:
   ```bash
   npm install
   ```

## Running the Application

To start the application, run:
```bash
npm start
```

The server will start on `http://localhost:3000` (or the port specified in `bin/www`).

## How This Project Was Created

This project was created using the following steps:

1. **Initialize the project with Express Generator:**
   ```bash
   npx express-generator --view=jade CRUD_NODE
   cd CRUD_NODE
   ```

2. **Install additional dependencies:**
   ```bash
   npm install mongoose
   ```

3. **Set up MongoDB connection:**
   - Added Mongoose connection in `app.js` to connect to a local MongoDB database named `demo_crud`.

4. **Create User model:**
   - Created `models/User.js` with a schema for users containing `name` and `email` fields.

5. **Implement CRUD operations:**
   - Updated `routes/users.js` to include full CRUD endpoints:
     - POST /users - Create a new user
     - GET /users - Get all users
     - GET /users/:id - Get a single user by ID
     - PUT /users/:id - Update a user by ID
     - DELETE /users/:id - Delete a user by ID

6. **Update package.json:**
   - Added Mongoose as a dependency.

## API Endpoints

### Users

- **GET /users**
  - Description: Retrieve all users
  - Response: Array of user objects

- **GET /users/:id**
  - Description: Retrieve a single user by ID
  - Parameters: `id` (User ID)
  - Response: User object or 404 if not found

- **POST /users**
  - Description: Create a new user
  - Body: `{ "name": "string", "email": "string" }`
  - Response: Created user object

- **PUT /users/:id**
  - Description: Update an existing user
  - Parameters: `id` (User ID)
  - Body: `{ "name": "string", "email": "string" }`
  - Response: Updated user object or 404 if not found

- **DELETE /users/:id**
  - Description: Delete a user
  - Parameters: `id` (User ID)
  - Response: Success message or 404 if not found

## Project Structure

```
CRUD_NODE/
├── bin/
│   └── www                 # Server startup script
├── models/
│   └── User.js             # User model schema
├── public/
│   ├── images/             # Static images
│   ├── javascripts/        # Client-side JavaScript
│   └── stylesheets/        # CSS styles
├── routes/
│   ├── index.js            # Home route
│   └── users.js            # User CRUD routes
├── views/                  # Jade templates
│   ├── error.jade
│   ├── index.jade
│   └── layout.jade
├── app.js                  # Main application file
├── package.json            # Dependencies and scripts
└── README.md               # This file
```

## Technologies Used

- **Express.js**: Web framework for Node.js
- **MongoDB**: NoSQL database
- **Mongoose**: ODM for MongoDB
- **Jade/Pug**: Templating engine
- **Morgan**: HTTP request logger
- **Cookie-parser**: Parse cookies
