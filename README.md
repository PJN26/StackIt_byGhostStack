# StackIt_byGhostStack
StackIt – A Minimal Q&amp;A Forum Platform



## PS --> StackIt – A Minimal Q&A Forum Platform

## Team Members
Pujan Parekh (TL) --> pujanparekhgondal@gmail.com<br/>
Het Virani --> hetvirani87@gmail.com<br/>
Hiren Vargiya --> hrvargiya.edu.124@gmail.com<br/>
Krishna Vyas --> vyaskrishna1311@gmail.com<br/>


# StackIT - AI-Powered Q&A Platform

A comprehensive Q&A platform built with React and Node.js, featuring AI-powered content generation and robust user management.

## Features

### 🔐 User Management
- **Sign-up Functionality**: Create new user accounts with email registration
- **Authorized Email Verification**: Secure email verification system to validate user accounts
- **JWT Authentication**: Secure token-based authentication with refresh tokens

### ❓ Question & Answer System
- **Adding Questions**: Users can post new questions to the platform
- **Answering Questions**: Community-driven answers with user responses
- **Upvoting**: Vote on questions and answers to highlight quality content

### 📚 Content Organization
- **Bookmarking**: Save questions and answers for later reference
- **Filtering**: Advanced search and filter options to find relevant content
- **Tagging**: Categorize questions with relevant tags for better organization

### 🤖 AI Features
- **Generative AI Editor**: AI-powered content editor using DeepSeek AI
- **Smart Question Descriptions**: Auto-generate comprehensive question descriptions
- **AI-Powered Content Enhancement**: Intelligent suggestions and content generation

## Tech Stack

### Frontend
- **React 18.3.1** - Modern UI library
- **React Router Dom** - Client-side routing
- **Axios** - HTTP client for API calls
- **React Hook Form** - Form management
- **React Toastify** - Toast notifications
- **React Icons** - Icon library
- **React Quill** - Rich text editor
- **Vite** - Build tool and development server

### Backend
- **Node.js & Express** - Server framework
- **MongoDB with Mongoose** - Database and ODM
- **JWT** - Authentication tokens
- **Bcrypt** - Password hashing
- **Nodemailer** - Email service
- **Multer** - File upload handling
- **DeepSeek AI** - AI content generation

## Prerequisites

Before running this project, make sure you have:

- **Node.js** (v16 or higher)
- **MongoDB** (local or cloud instance)
- **DeepSeek AI API Key** (from [platform.deepseek.com](https://platform.deepseek.com))
- **Gmail Account** (for email verification)

## Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd StackIT
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env
```

#### Configure Environment Variables

Create a `.env` file in the backend directory with the following variables:

```env
# Server Configuration
PORT=5000
NODE_ENV=development
CORS_ORIGIN=http://localhost:3000

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/stackit
# For MongoDB Atlas: mongodb+srv://username:password@cluster.mongodb.net/stackit

# JWT Configuration
JWT_SECRET=your_super_secure_jwt_secret_here
JWT_EXPIRY=15m
JWT_REFRESH_SECRET=your_super_secure_refresh_secret_here
JWT_REFRESH_EXPIRY=30d

# Email Configuration (Gmail)
EMAIL_SERVICE=smtp
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password_here
EMAIL_FROM=StackIt <your_email@gmail.com>

# DeepSeek AI Configuration
DEEPSEEK_API_KEY=your_deepseek_api_key_here
```

#### Email Setup Instructions

1. **Enable 2-Factor Authentication** on your Gmail account
2. **Generate App Password**:
   - Go to Google Account settings
   - Security → 2-Step Verification → App passwords
   - Generate a new app password
   - Use this password in `EMAIL_PASS`

#### DeepSeek AI Setup

1. Visit [platform.deepseek.com](https://platform.deepseek.com)
2. Sign up for an account
3. Generate an API key
4. Add the key to `DEEPSEEK_API_KEY` in your `.env` file

### 3. Frontend Setup

```bash
# Navigate to frontend directory (from project root)
cd frontend

# Install dependencies
npm install
```

### 4. Database Setup

Make sure MongoDB is running:

```bash
# For local MongoDB
mongod

# For MongoDB service on Windows
net start MongoDB

# For MongoDB service on macOS/Linux
sudo systemctl start mongod
```

## Running the Application

### Development Mode

#### Terminal 1 - Backend Server
```bash
cd backend
npm run dev
```
Backend will run on `http://localhost:5000`

#### Terminal 2 - Frontend Development Server
```bash
cd frontend
npm run dev
```
Frontend will run on `http://localhost:3000`

### Production Build

```bash
# Build frontend
cd frontend
npm run build

# Start backend in production
cd ../backend
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/verify-email` - Email verification
- `POST /api/auth/refresh-token` - Refresh JWT token

### Questions
- `GET /api/questions` - Get all questions (with filters)
- `POST /api/questions` - Create new question
- `GET /api/questions/:id` - Get specific question
- `PUT /api/questions/:id/upvote` - Upvote question
- `PUT /api/questions/:id/bookmark` - Bookmark question

### Answers
- `POST /api/answers` - Create new answer
- `PUT /api/answers/:id/upvote` - Upvote answer

### AI Features
- `POST /api/ai/generate-description` - Generate AI description for questions

## Usage Guide

### Getting Started

1. **Sign Up**: Create a new account with your email
2. **Verify Email**: Check your email and click the verification link
3. **Login**: Access your account with verified credentials
4. **Explore**: Browse questions using filters and tags

### Key Features

#### 🤖 AI-Powered Question Creation
1. Go to "Ask Question" page
2. Enter your question title (minimum 15 characters)
3. Click "Generate with AI" button
4. AI will create a comprehensive description
5. Edit if needed and add relevant tags
6. Submit your question

#### 🔖 Bookmarking & Organization
- Click the bookmark icon on any question to save it
- Access your bookmarks from your profile
- Use tags to filter and organize content

#### 👍 Community Engagement
- Upvote helpful questions and answers
- Provide detailed answers to help others
- Use the rich text editor for formatted responses

## Project Structure

```
StackIT/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middleware/
│   │   └── utils/
│   ├── .env
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── utils/
│   ├── package.json
│   └── index.html
└── README.md
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Troubleshooting

### Common Issues

1. **MongoDB Connection Error**
   - Ensure MongoDB is running
   - Check MONGODB_URI in .env file
   - Verify database permissions

2. **Email Verification Not Working**
   - Check Gmail app password setup
   - Verify EMAIL_* variables in .env
   - Ensure Gmail 2FA is enabled

3. **AI Generation Failing**
   - Verify DeepSeek API key
   - Check API key permissions
   - Ensure proper internet connection

4. **Frontend Not Loading**
   - Check if backend is running on port 5000
   - Verify CORS_ORIGIN setting
   - Clear browser cache

### Environment Variables Checklist

- [ ] PORT (default: 5000)
- [ ] MONGODB_URI (local or cloud)
- [ ] JWT_SECRET (strong random string)
- [ ] JWT_REFRESH_SECRET (different from JWT_SECRET)
- [ ] EMAIL_USER (your Gmail)
- [ ] EMAIL_PASS (Gmail app password)
- [ ] DEEPSEEK_API_KEY (from DeepSeek platform)

## Support

For support, email goststack87@gmail.com or join our community discussions.

---
