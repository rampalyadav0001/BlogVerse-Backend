# BlogVerse Backend

A robust REST API backend for a modern blogging platform built with Node.js, Express, and MongoDB.

## 🚀 Features

- User authentication and authorization
- CRUD operations for blog posts
- Comment system
- User profiles
- Category management
- Search functionality
- Image upload support
- API rate limiting
- JWT-based authentication

## 📋 Prerequisites

- Node.js (v14.0.0 or higher)
- MongoDB
- npm or yarn

## 🛠️ Installation

1. Clone the repository:
```bash
git clone https://github.com/rampalyadav0001/BlogVerse-Backend.git
cd BlogVerse-Backend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory and add your environment variables:
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

4. Start the server:
```bash
# Development mode
npm run dev

# Production mode
npm start
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Blog Posts
- `GET /api/posts` - Get all posts
- `GET /api/posts/:id` - Get single post
- `POST /api/posts` - Create new post
- `PUT /api/posts/:id` - Update post
- `DELETE /api/posts/:id` - Delete post

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `DELETE /api/users/profile` - Delete user account

### Comments
- `POST /api/posts/:id/comments` - Add comment to post
- `PUT /api/posts/:id/comments/:commentId` - Update comment
- `DELETE /api/posts/:id/comments/:commentId` - Delete comment

## 🔒 Authentication

The API uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```
Authorization: Bearer <your_jwt_token>
```

## 🗄️ Database Schema

### User
```javascript
{
  username: String,
  email: String,
  password: String,
  profilePic: String,
  bio: String,
  createdAt: Date
}
```

### Post
```javascript
{
  title: String,
  content: String,
  author: ObjectId,
  categories: [String],
  tags: [String],
  image: String,
  createdAt: Date,
  updatedAt: Date
}
```

## 🛡️ Error Handling

The API uses consistent error response format:

```javascript
{
  success: false,
  message: "Error message here",
  error: error_details // (in development)
}
```

## 📝 Testing

Run the test suite:

```bash
npm test
```

Run tests with coverage:

```bash
npm run test:coverage
```

## 🔨 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Rampal Yadav** - [GitHub Profile](https://github.com/rampalyadav0001)

## 🙏 Acknowledgments

- Express.js team
- MongoDB team
- All contributors who helped with the project
