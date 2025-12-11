# MERN Blog Platform

<div align="center">

![MERN Stack](https://img.shields.io/badge/MERN-Stack-00D9FF?style=for-the-badge&logo=mongodb&logoColor=white)
![React](https://img.shields.io/badge/React-19.2.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-7.6-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

A modern, full-stack blogging platform built with the MERN stack (MongoDB, Express, React, Node.js). Create, edit, and manage blog posts with a beautiful dark-themed UI, image uploads, and user authentication.

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [API Documentation](#-api-documentation) • [Project Structure](#-project-structure)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [API Documentation](#-api-documentation)
- [Project Structure](#-project-structure)
- [Authentication](#-authentication)
- [File Upload](#-file-upload)
- [Deployment](#-deployment)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

MERN Blog is a comprehensive blogging platform that allows users to:
- Create and manage blog posts
- Upload images to enhance content
- Tag posts for better discoverability
- Edit and delete their own posts
- View posts from the community
- Manage user profiles and dashboards

The application features a modern dark-themed UI with smooth animations, gradient effects, and a responsive design that works seamlessly across all devices.

---

## ✨ Features

### Core Features
- ✅ **User Authentication** - Secure registration and login with JWT
- ✅ **Blog Post Management** - Create, read, update, and delete posts
- ✅ **Image Upload** - Upload and display images with posts (5MB limit)
- ✅ **Tag System** - Add tags to posts for categorization
- ✅ **User Dashboard** - View and manage your own posts
- ✅ **User Profile** - Manage account information
- ✅ **Responsive Design** - Works on desktop, tablet, and mobile devices

### UI/UX Features
- 🎨 **Modern Dark Theme** - Beautiful gradient-based dark theme
- ✨ **Smooth Animations** - Fade-in, slide-in, and hover effects
- 🎭 **Glassmorphism** - Modern glass-like effects on header
- 🌈 **Gradient Effects** - Beautiful gradient backgrounds and text
- 📱 **Mobile Responsive** - Optimized for all screen sizes
- ⚡ **Fast Performance** - Optimized with React and Redux

### Pages
- 🏠 **Home** - View all blog posts
- 📝 **Create Post** - Create new blog posts
- ✏️ **Edit Post** - Edit existing posts
- 👁️ **Post Details** - View individual post with full content
- 👤 **Profile** - User profile management
- 📊 **Dashboard** - User's post management
- 📞 **Contact** - Contact form
- ℹ️ **About** - Platform information

---

## 🛠️ Tech Stack

### Frontend
- **React 19.2.0** - UI library
- **Redux Toolkit 2.11.1** - State management
- **React Router DOM 7.10.1** - Routing
- **Axios 1.13.2** - HTTP client
- **Vite 7.2.4** - Build tool
- **CSS3** - Styling with animations

### Backend
- **Node.js** - Runtime environment
- **Express.js 4.18.2** - Web framework
- **MongoDB 7.6.3** - Database
- **Mongoose 7.6.3** - ODM
- **JWT 9.0.3** - Authentication
- **Bcryptjs 3.0.3** - Password hashing
- **Multer 2.0.2** - File upload handling

### Development Tools
- **Nodemon** - Auto-restart server
- **Concurrently** - Run multiple commands
- **ESLint** - Code linting
- **Vitest** - Testing framework

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher)
- **npm** (v9 or higher) or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)
- **Git** (for cloning the repository)

---

## 🚀 Installation

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd mern-blog1
```

### Step 2: Install Dependencies

Install root dependencies:
```bash
npm install
```

Install server dependencies:
```bash
cd server
npm install
```

Install client dependencies:
```bash
cd ../client
npm install
```

### Step 3: Environment Configuration

Create a `.env` file in the `server` directory:

```bash
cd server
touch .env
```

Add the following environment variables:

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/mern-blog
JWT_SECRET=your-secret-key-change-this-in-production
```

**For MongoDB Atlas:**
```env
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/mern-blog?retryWrites=true&w=majority
```

Create a `.env` file in the `client` directory:

```bash
cd ../client
touch .env
```

Add:
```env
VITE_API_URL=http://localhost:5000/api
```

### Step 4: Create Uploads Directory

```bash
cd ../server
mkdir uploads
```

---

## ⚙️ Configuration

### Server Configuration

The server runs on port `5000` by default. You can change this in the `.env` file.

**Important Environment Variables:**
- `PORT` - Server port (default: 5000)
- `MONGO_URI` - MongoDB connection string
- `JWT_SECRET` - Secret key for JWT tokens (use a strong random string in production)

### Client Configuration

The client runs on port `5173` by default (Vite default).

**Environment Variables:**
- `VITE_API_URL` - Backend API URL (default: http://localhost:5000/api)

### MongoDB Setup

**Option 1: Local MongoDB**
1. Install MongoDB locally
2. Start MongoDB service
3. Use connection string: `mongodb://localhost:27017/mern-blog`

**Option 2: MongoDB Atlas (Cloud)**
1. Create account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a cluster
3. Get connection string
4. Update `MONGO_URI` in `.env`

---

## 🎮 Usage

### Development Mode

Run both server and client concurrently:

```bash
npm run dev
```

This will start:
- **Server** on `http://localhost:5000`
- **Client** on `http://localhost:5173`

### Run Separately

**Start Server Only:**
```bash
npm run server
# or
cd server && npm run dev
```

**Start Client Only:**
```bash
npm run client
# or
cd client && npm run dev
```

### Production Build

**Build Client:**
```bash
cd client
npm run build
```

**Start Server (Production):**
```bash
cd server
npm start
```

---

## 📚 API Documentation

### Base URL
```
http://localhost:5000/api
```

### Authentication Endpoints

#### Register User
```http
POST /api/auth/register
Content-Type: application/json

{
  "username": "johndoe",
  "password": "password123"
}
```

**Response:**
```json
{
  "message": "User registered successfully"
}
```

#### Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "username": "johndoe",
  "password": "password123"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "username": "johndoe"
  }
}
```

### Post Endpoints

#### Get All Posts
```http
GET /api/posts
```

**Response:**
```json
[
  {
    "_id": "507f1f77bcf86cd799439011",
    "title": "My First Post",
    "content": "This is the content...",
    "author": {
      "_id": "507f1f77bcf86cd799439012",
      "username": "johndoe"
    },
    "tags": ["tech", "blogging"],
    "image": "uploads/image-1234567890.jpg",
    "createdAt": "2024-01-01T00:00:00.000Z",
    "updatedAt": "2024-01-01T00:00:00.000Z"
  }
]
```

#### Get Single Post
```http
GET /api/posts/:id
```

#### Create Post
```http
POST /api/posts
Authorization: Bearer <token>
Content-Type: multipart/form-data

Form Data:
- title: "Post Title"
- content: "Post content..."
- tags: "tag1, tag2, tag3"
- image: <file> (optional)
```

**Response:**
```json
{
  "_id": "507f1f77bcf86cd799439011",
  "title": "Post Title",
  "content": "Post content...",
  "author": "507f1f77bcf86cd799439012",
  "tags": ["tag1", "tag2", "tag3"],
  "image": "uploads/image-1234567890.jpg",
  "createdAt": "2024-01-01T00:00:00.000Z"
}
```

#### Update Post
```http
PUT /api/posts/:id
Authorization: Bearer <token>
Content-Type: multipart/form-data

Form Data:
- title: "Updated Title"
- content: "Updated content..."
- tags: "tag1, tag2"
- image: <file> (optional)
```

#### Delete Post
```http
DELETE /api/posts/:id
Authorization: Bearer <token>
```

**Response:**
```json
{
  "message": "Post deleted"
}
```

### Error Responses

All endpoints may return the following error responses:

```json
{
  "message": "Error message here"
}
```

**Status Codes:**
- `200` - Success
- `201` - Created
- `400` - Bad Request
- `401` - Unauthorized
- `403` - Forbidden
- `404` - Not Found
- `500` - Server Error

---

## 📁 Project Structure

```
mern-blog1/
│
├── client/                 # React frontend application
│   ├── public/            # Static assets
│   ├── src/
│   │   ├── components/   # Reusable components
│   │   │   ├── Header.jsx
│   │   │   ├── Layout.jsx
│   │   │   └── PostCard.jsx
│   │   ├── features/     # Redux slices
│   │   │   ├── auth/
│   │   │   │   └── authSlice.js
│   │   │   └── posts/
│   │   │       └── postSlice.js
│   │   ├── pages/         # Page components
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── CreatePost.jsx
│   │   │   ├── EditPost.jsx
│   │   │   ├── PostDetails.jsx
│   │   │   ├── Profile.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Contact.jsx
│   │   │   └── About.jsx
│   │   ├── store/         # Redux store
│   │   │   └── store.js
│   │   ├── App.jsx        # Main app component
│   │   ├── main.jsx       # Entry point
│   │   └── index.css      # Global styles
│   ├── package.json
│   └── vite.config.js
│
├── server/                # Node.js backend application
│   ├── controllers/       # Route controllers
│   │   ├── authController.js
│   │   └── postController.js
│   ├── middleware/        # Custom middleware
│   │   ├── authMiddleware.js
│   │   └── uploadMiddleware.js
│   ├── models/           # Mongoose models
│   │   ├── User.js
│   │   └── Post.js
│   ├── routes/           # API routes
│   │   ├── authRoutes.js
│   │   └── postRoutes.js
│   ├── uploads/          # Uploaded files directory
│   ├── server.js         # Server entry point
│   └── package.json
│
├── package.json          # Root package.json
└── README.md            # This file
```

---

## 🔐 Authentication

### How It Works

1. **Registration**: User creates account with username and password
2. **Password Hashing**: Password is hashed using bcryptjs (10 rounds)
3. **Login**: User logs in with credentials
4. **JWT Token**: Server generates JWT token (expires in 1 hour)
5. **Token Storage**: Token stored in localStorage
6. **Protected Routes**: Token sent in Authorization header

### Token Format

```
Authorization: Bearer <token>
```

### Protected Endpoints

All post creation, update, and deletion endpoints require authentication:
- `POST /api/posts`
- `PUT /api/posts/:id`
- `DELETE /api/posts/:id`

---

## 📤 File Upload

### Supported Formats
- JPEG/JPG
- PNG
- GIF

### File Size Limit
- Maximum: 5MB

### Upload Process

1. User selects image file
2. FormData is created with file
3. File sent to server via POST request
4. Multer middleware handles upload
5. File saved to `server/uploads/` directory
6. File path stored in database
7. Image accessible via `/uploads/filename.jpg`

### Image URL Format

```
http://localhost:5000/uploads/image-1234567890.jpg
```

---

## 🚀 Deployment

### Backend Deployment (Heroku Example)

1. **Install Heroku CLI**
2. **Login to Heroku**
   ```bash
   heroku login
   ```

3. **Create Heroku App**
   ```bash
   cd server
   heroku create your-app-name
   ```

4. **Set Environment Variables**
   ```bash
   heroku config:set MONGO_URI=your-mongodb-uri
   heroku config:set JWT_SECRET=your-secret-key
   heroku config:set PORT=5000
   ```

5. **Deploy**
   ```bash
   git push heroku main
   ```

### Frontend Deployment (Vercel Example)

1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Build Project**
   ```bash
   cd client
   npm run build
   ```

3. **Deploy**
   ```bash
   vercel
   ```

4. **Set Environment Variables**
   - `VITE_API_URL` - Your backend API URL

### Environment Variables for Production

**Backend (.env):**
```env
PORT=5000
MONGO_URI=your-production-mongodb-uri
JWT_SECRET=your-strong-secret-key
NODE_ENV=production
```

**Frontend (.env):**
```env
VITE_API_URL=https://your-backend-api.com/api
```

---

## 🔧 Troubleshooting

### Common Issues

#### MongoDB Connection Error
```
Error: MongoDB Connection Error
```
**Solution:**
- Check MongoDB is running
- Verify MONGO_URI in .env file
- Check network connectivity

#### Port Already in Use
```
Error: Port 5000 is already in use
```
**Solution:**
- Change PORT in .env file
- Kill process using the port: `lsof -ti:5000 | xargs kill`

#### CORS Error
```
Access-Control-Allow-Origin error
```
**Solution:**
- Verify CORS is enabled in server.js
- Check API URL in client .env

#### Image Upload Fails
```
Error: File upload error
```
**Solution:**
- Check file size (max 5MB)
- Verify file format (JPEG, PNG, GIF)
- Ensure uploads directory exists
- Check file permissions

#### JWT Token Invalid
```
Error: Invalid token
```
**Solution:**
- Clear localStorage
- Login again
- Check JWT_SECRET matches

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make your changes**
4. **Commit your changes**
   ```bash
   git commit -m "Add amazing feature"
   ```

5. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open a Pull Request**

### Code Style

- Use ESLint for code linting
- Follow React best practices
- Write meaningful commit messages
- Add comments for complex logic

---

## 📝 License

This project is licensed under the ISC License.

---

## 👨‍💻 Author

Created with ❤️ using the MERN stack

---

## 🙏 Acknowledgments

- React team for the amazing framework
- MongoDB for the database solution
- Express.js for the web framework
- All open-source contributors

---

## 📞 Support

For support, email aryanahmad478@gmail.com or open an issue in the repository.

---

<div align="center">

**Made with ❤️ using MERN Stack**

⭐ Star this repo if you find it helpful!

</div>

