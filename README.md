# Sweet Shop Management System

A full-stack web application for managing a sweet shop inventory, built with Node.js, MongoDB, and React. This project demonstrates modern web development practices including RESTful API design, JWT authentication, and responsive UI design.

![Sweet Shop](https://img.shields.io/badge/Sweet-Shop-pink?style=for-the-badge)
![Node.js](https://img.shields.io/badge/Node.js-18+-green?style=for-the-badge&logo=node.js)
![React](https://img.shields.io/badge/React-18+-blue?style=for-the-badge&logo=react)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green?style=for-the-badge&logo=mongodb)

## Features

### Backend (Node.js/Express)
- ✅ RESTful API with Express.js
- ✅ MongoDB Atlas database integration
- ✅ JWT-based authentication
- ✅ User roles (User/Admin)
- ✅ CRUD operations for sweets
- ✅ Search and filter functionality
- ✅ Inventory management (purchase/restock)
- ✅ Comprehensive test coverage

### Frontend (React)
- ✅ Modern, responsive UI design
- ✅ User authentication (Login/Register)
- ✅ Dashboard with sweet listings
- ✅ Real-time search and filtering
- ✅ Purchase functionality
- ✅ Admin panel for managing sweets
- ✅ Smooth animations and transitions

## Project Structure

```
sweet-shop-management-system/
├── backend/
│   ├── src/
│   │   ├── __tests__/          # Test files
│   │   ├── controllers/        # Route controllers
│   │   ├── middleware/         # Auth middleware
│   │   ├── models/             # MongoDB models
│   │   ├── routes/             # API routes
│   │   └── server.js           # Entry point
│   ├── package.json
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── components/         # React components
│   │   ├── context/            # React context
│   │   ├── pages/              # Page components
│   │   └── main.jsx            # Entry point
│   ├── package.json
│   └── vite.config.js
└── README.md
```

## Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- MongoDB Atlas account (or local MongoDB instance)

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd sweet-shop-management-system
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the `backend` directory:

```env
PORT=5000
MONGODB_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_super_secret_jwt_key
NODE_ENV=development
```

**Getting MongoDB Atlas Connection String:**
1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a free cluster
3. Click "Connect" → "Connect your application"
4. Copy the connection string
5. Replace `<password>` with your database password
6. Replace `<dbname>` with `sweet-shop` (or your preferred database name)

### 3. Frontend Setup

```bash
cd frontend
npm install
```

### 4. Running the Application

**Start Backend Server:**
```bash
cd backend
npm run dev
```
The backend will run on `http://localhost:5000`

**Start Frontend Development Server:**
```bash
cd frontend
npm run dev
```
The frontend will run on `http://localhost:3000`

### 5. Running Tests

```bash
cd backend
npm test
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user

### Sweets (Protected - Requires JWT Token)
- `GET /api/sweets` - Get all sweets
- `GET /api/sweets/search` - Search sweets (query params: name, category, minPrice, maxPrice)
- `POST /api/sweets` - Create a new sweet (Admin only)
- `PUT /api/sweets/:id` - Update a sweet (Admin only)
- `DELETE /api/sweets/:id` - Delete a sweet (Admin only)
- `POST /api/sweets/:id/purchase` - Purchase a sweet
- `POST /api/sweets/:id/restock` - Restock a sweet (Admin only)

### Example API Request

```bash
# Login
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"user@example.com","password":"password123"}'

# Get all sweets (with token)
curl -X GET http://localhost:5000/api/sweets \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

## Usage Guide

### For Regular Users
1. Register/Login to your account
2. Browse available sweets on the dashboard
3. Use the search bar to find specific sweets
4. Click "Purchase" to buy a sweet (quantity decreases automatically)
5. Purchase button is disabled when a sweet is out of stock

### For Admin Users
1. Register/Login with admin role
2. All regular user features are available
3. Click "Add New Sweet" to create a new sweet item
4. Click the edit icon (✏️) to update sweet details
5. Click the delete icon (🗑️) to remove a sweet
6. Click the restock icon (📦) to add more quantity to a sweet

## Screenshots

### Login Page
![Login Page](/login.png)

### Dashboard
![Dashboard](/dashboard.png)

### Admin Panel
![Admin Panel](/admin.png)

## Test Coverage

The backend includes comprehensive test coverage for:
- User authentication (register/login)
- Sweet CRUD operations
- Search functionality
- Purchase and restock operations
- Admin authorization

Run tests with:
```bash
cd backend
npm test
```

## Technologies Used

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database (via Mongoose)
- **JWT** - Authentication
- **bcryptjs** - Password hashing
- **Jest** - Testing framework

### Frontend
- **React** - UI library
- **React Router** - Routing
- **Axios** - HTTP client
- **Vite** - Build tool
- **React Icons** - Icon library

## Development Workflow

This project follows Test-Driven Development (TDD) principles:
1. **Red**: Write failing tests first
2. **Green**: Implement functionality to pass tests
3. **Refactor**: Improve code while keeping tests green

## Deployment

### Backend Deployment (Heroku/Railway/Render)
1. Set environment variables in your hosting platform
2. Ensure MongoDB Atlas allows connections from your server IP
3. Deploy the backend code

### Frontend Deployment (Vercel/Netlify)
1. Build the frontend: `npm run build`
2. Deploy the `dist` folder
3. Update API URLs if needed

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Write/update tests
5. Submit a pull request

## License

This project is open source and available under the MIT License.

---

## My AI Usage

### AI Tools Used
During the development of this project, I utilized **Cursor AI** (an AI-powered coding assistant) to help with various aspects of the development process.

### How AI Was Used

1. **Code Generation & Boilerplate**
   - Used AI to generate initial project structure and configuration files (package.json, vite.config.js, etc.)
   - Generated boilerplate code for Express routes, controllers, and middleware
   - Created React component templates with proper structure

2. **Code Conversion**
   - Initially created the backend in TypeScript, then used AI assistance to convert all TypeScript files to plain JavaScript as per requirements
   - AI helped maintain code functionality while converting type annotations and interfaces

3. **Best Practices & Patterns**
   - Consulted AI for best practices in Express.js route organization
   - Got suggestions for React component structure and state management
   - Received guidance on MongoDB schema design and Mongoose usage

4. **Debugging & Problem Solving**
   - Used AI to troubleshoot import/export issues when converting from TypeScript to JavaScript
   - Got help fixing module resolution problems with ES6 imports
   - Received suggestions for handling async/await patterns

5. **Documentation**
   - AI assisted in structuring the README file
   - Helped format API endpoint documentation
   - Generated clear setup instructions

### Reflection on AI Impact

**Positive Impacts:**
- **Speed**: Significantly accelerated development by generating boilerplate code and common patterns
- **Learning**: AI suggestions helped me understand modern best practices and patterns
- **Consistency**: AI helped maintain consistent code style and structure across the project
- **Error Prevention**: AI caught potential issues early, such as missing imports or incorrect syntax

**Challenges & Learning:**
- **Over-reliance**: Initially, I found myself relying too heavily on AI suggestions without fully understanding the code
- **Context Understanding**: Sometimes AI suggestions needed refinement to match the specific project requirements
- **Debugging**: When AI-generated code had issues, it required careful debugging to understand the root cause

**Responsible Usage:**
- I reviewed and understood all AI-generated code before using it
- Modified and customized AI suggestions to fit the project's specific needs
- Wrote all tests manually to ensure I understood the functionality
- Used AI as a tool to enhance productivity, not replace critical thinking

**Conclusion:**
AI tools like Cursor AI proved to be valuable assistants in this project, helping with repetitive tasks and providing learning opportunities. However, the core logic, architecture decisions, and understanding of the codebase remain my own. The AI served as a powerful pair-programming partner, but I maintained full control and understanding of the code throughout the development process.

---

## Contact

For questions or support, please open an issue in the repository.

**Happy Coding! 🍬**

