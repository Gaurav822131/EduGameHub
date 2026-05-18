# 🎓 EduGameHub - AI-Powered Gamified Learning Platform

<div align="center">

![EduGameHub Banner](https://img.shields.io/badge/EduGameHub-AI%20Learning-blue?style=for-the-badge)
[![Live Demo](https://img.shields.io/badge/Live-Demo-success?style=for-the-badge)](https://edu-gamehub.vercel.app)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black?style=for-the-badge&logo=github)](https://github.com/Gaurav822131/EduGameHub)

**A next-generation learning platform that combines AI-powered education with gamification to create an engaging and effective learning experience.**

[Features](#-features) • [Tech Stack](#-tech-stack) • [Installation](#-installation) • [API Documentation](#-api-documentation) • [Contributing](#-contributing)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [API Documentation](#-api-documentation)
- [Project Structure](#-project-structure)
- [Deployment](#-deployment)
- [Testing](#-testing)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

EduGameHub is a comprehensive full-stack learning platform built with the MERN stack that revolutionizes online education through:

- 🤖 **AI-Powered Learning**: Intelligent question generation and personalized study recommendations
- 🎮 **Gamification**: XP points, badges, streaks, leaderboards, and achievements
- 👥 **Social Learning**: Study groups, friend systems, and collaborative features
- 📊 **Advanced Analytics**: Detailed performance tracking and learning insights
- ⚡ **Real-Time Features**: Live multiplayer quiz rooms with Socket.IO
- 🎯 **Adaptive Learning**: Difficulty adjustment based on performance
- 📱 **Progressive Web App**: Offline support and mobile-friendly design

---

## ✨ Features

### 🔐 Authentication & Authorization
- JWT-based authentication with secure token management
- Google OAuth 2.0 integration for seamless login
- Role-based access control (Admin, Premium Instructor, User)
- Session management with Redis caching

### 📝 Quiz Management
- **Create & Manage**: Comprehensive quiz creation with multiple question types
- **AI Generation**: Automatic question generation using Google Gemini AI
- **Adaptive Quizzes**: Dynamic difficulty adjustment based on user performance
- **Written Tests**: Support for essay-type questions with AI evaluation
- **Bookmarking**: Save favorite quizzes for quick access
- **Categories**: Organized by subjects and difficulty levels

### 🎮 Gamification System
- **XP Points**: Earn experience points for completing quizzes
- **Badges & Achievements**: Unlock rewards for milestones
- **Study Streaks**: Daily streak tracking with bonus rewards
- **Leaderboards**: Global and category-specific rankings
- **Daily Challenges**: Special quests for extra rewards
- **Tournaments**: Competitive events with prizes

### 🤖 AI-Powered Features
- **AI Study Buddy**: Personalized learning assistant
- **Smart Recommendations**: ML-based quiz suggestions
- **Question Generation**: Automatic quiz creation from topics
- **Performance Analysis**: AI-driven insights and improvement tips
- **Spaced Repetition**: Intelligent review scheduling
- **Cognitive Metrics**: Track learning patterns and retention

### 👥 Social & Collaborative
- **Study Groups**: Create and join learning communities
- **Friend System**: Connect with other learners
- **Activity Feed**: See what friends are learning
- **Real-Time Multiplayer**: Compete in live quiz rooms
- **Group Challenges**: Collaborative learning goals
- **Social Sharing**: Share achievements and progress

### 📊 Analytics & Insights
- **Performance Dashboard**: Comprehensive learning analytics
- **Progress Tracking**: Visual representation of improvement
- **Time Analytics**: Study time and efficiency metrics
- **Strength/Weakness Analysis**: Identify areas for improvement
- **Learning Path Recommendations**: Personalized study plans
- **Export Reports**: Download detailed performance reports (PDF)

### 🎨 User Experience
- **Multiple Themes**: Dark mode, light mode, and custom themes
- **Responsive Design**: Optimized for all devices
- **Offline Support**: PWA with offline quiz taking
- **Keyboard Shortcuts**: Power user features
- **Accessibility**: WCAG compliant design
- **Notifications**: Real-time updates and reminders

---

## 🛠 Tech Stack

### Frontend
| Technology | Purpose |
|------------|---------|
| **React 19** | UI framework with latest features |
| **Vite** | Fast build tool and dev server |
| **React Router v7** | Client-side routing |
| **Axios** | HTTP client for API calls |
| **Framer Motion** | Smooth animations |
| **Chart.js** | Data visualization |
| **Socket.IO Client** | Real-time communication |
| **jsPDF** | PDF report generation |

### Backend
| Technology | Purpose |
|------------|---------|
| **Node.js** | JavaScript runtime |
| **Express.js** | Web application framework |
| **MongoDB** | NoSQL database |
| **Mongoose** | MongoDB ODM |
| **JWT** | Authentication tokens |
| **Passport.js** | OAuth strategies |
| **Socket.IO** | WebSocket server |
| **Redis** | Caching and session store |
| **Google Gemini AI** | AI question generation |
| **Winston** | Logging system |

### DevOps & Tools
| Technology | Purpose |
|------------|---------|
| **Vercel** | Frontend hosting |
| **MongoDB Atlas** | Cloud database |
| **Redis Cloud** | Managed Redis instance |
| **GitHub Actions** | CI/CD pipelines |
| **ESLint** | Code linting |
| **Jest & Vitest** | Testing frameworks |
| **Helmet** | Security middleware |

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                         Client Layer                         │
│  (React SPA + PWA + Socket.IO Client)                       │
└────────────────────┬────────────────────────────────────────┘
                     │
                     │ HTTPS/WSS
                     │
┌────────────────────▼────────────────────────────────────────┐
│                      API Gateway Layer                       │
│  (Express.js + Middleware + Rate Limiting)                  │
└────────────────────┬────────────────────────────────────────┘
                     │
        ┌────────────┼────────────┐
        │            │            │
┌───────▼──────┐ ┌──▼─────┐ ┌───▼──────────┐
│   Business   │ │ Socket │ │   AI Service │
│     Logic    │ │  .IO   │ │   (Gemini)   │
│ (Controllers)│ │ Server │ │              │
└───────┬──────┘ └────────┘ └──────────────┘
        │
┌───────▼──────────────────────────────────┐
│          Data Access Layer               │
│  (Mongoose Models + Services)            │
└───────┬──────────────────────────────────┘
        │
    ┌───┴────┐
┌───▼───┐ ┌──▼────┐
│MongoDB│ │ Redis │
│ Atlas │ │ Cache │
└───────┘ └───────┘
```

---

## 🚀 Installation

### Prerequisites

- **Node.js** (v18 or higher)
- **MongoDB** (v6 or higher)
- **Redis** (v7 or higher)
- **npm** or **yarn**
- **Git**

### Step 1: Clone Repository

```bash
git clone https://github.com/Gaurav822131/EduGameHub.git
cd EduGameHub
```

### Step 2: Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:

```env
# Server Configuration
PORT=4000
NODE_ENV=development

# Database
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/edugamehub?retryWrites=true&w=majority

# JWT Authentication
JWT_SECRET=your_super_secret_jwt_key_here_min_32_chars
JWT_EXPIRE=7d

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_CALLBACK_URL=http://localhost:4000/api/users/google/callback

# Session
GOOGLE_SECRET=your_session_secret_key

# Redis Cache
REDIS_URL=redis://localhost:6379
REDIS_PASSWORD=your_redis_password

# Frontend URL
FRONTEND_URL=http://localhost:5173

# AI Services
GOOGLE_GEMINI_API_KEY=your_gemini_api_key

# Email Service (EmailJS)
EMAILJS_SERVICE_ID=your_service_id
EMAILJS_TEMPLATE_ID=your_template_id
EMAILJS_PUBLIC_KEY=your_public_key
```

Start the backend server:

```bash
npm start
```

Backend will run on `http://localhost:4000`

### Step 3: Frontend Setup

```bash
cd ../frontend
npm install
```

Create a `.env` file in the frontend directory:

```env
VITE_API_URL=http://localhost:4000
VITE_SOCKET_URL=http://localhost:4000
VITE_GOOGLE_CLIENT_ID=your_google_client_id
VITE_EMAILJS_SERVICE_ID=your_service_id
VITE_EMAILJS_TEMPLATE_ID=your_template_id
VITE_EMAILJS_PUBLIC_KEY=your_public_key
```

Start the development server:

```bash
npm run dev
```

Frontend will run on `http://localhost:5173`

### Step 4: Access the Application

Open your browser and navigate to:
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:4000/api

---

## ⚙️ Configuration

### MongoDB Setup

1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Add your IP address to the whitelist
4. Create a database user
5. Get your connection string and add it to `.env`

### Redis Setup

**Option 1: Local Redis**
```bash
# Install Redis (Ubuntu/Debian)
sudo apt-get install redis-server

# Start Redis
redis-server
```

**Option 2: Redis Cloud**
1. Sign up at [Redis Cloud](https://redis.com/try-free/)
2. Create a new database
3. Copy the connection URL to `.env`

### Google OAuth Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized redirect URIs:
   - `http://localhost:4000/api/users/google/callback`
   - `https://your-domain.com/api/users/google/callback`
6. Copy Client ID and Secret to `.env`

### Google Gemini AI Setup

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create an API key
3. Add it to your `.env` file

---

## 📚 API Documentation

### Authentication Endpoints

#### Register User
```http
POST /api/users/register
Content-Type: application/json

{
  "username": "johndoe",
  "email": "john@example.com",
  "password": "SecurePass123!",
  "role": "user"
}
```

#### Login
```http
POST /api/users/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "SecurePass123!"
}
```

#### Google OAuth
```http
GET /api/users/google
GET /api/users/google/callback
```

#### Logout
```http
POST /api/users/logout
Authorization: Bearer <token>
```

### Quiz Endpoints

#### Get All Quizzes
```http
GET /api/quizzes?category=math&difficulty=medium&page=1&limit=10
Authorization: Bearer <token>
```

#### Get Quiz by ID
```http
GET /api/quizzes/:id
Authorization: Bearer <token>
```

#### Create Quiz
```http
POST /api/quizzes
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "JavaScript Basics",
  "description": "Test your JS knowledge",
  "category": "programming",
  "difficulty": "medium",
  "questions": [
    {
      "question": "What is closure?",
      "options": ["A", "B", "C", "D"],
      "correctAnswer": 0,
      "explanation": "Detailed explanation..."
    }
  ]
}
```

#### Submit Quiz
```http
POST /api/quizzes/:id/submit
Authorization: Bearer <token>
Content-Type: application/json

{
  "answers": [0, 2, 1, 3],
  "timeSpent": 300
}
```

#### Delete Quiz
```http
DELETE /api/quizzes/:id
Authorization: Bearer <token>
```

### User Endpoints

#### Get Profile
```http
GET /api/users/me
Authorization: Bearer <token>
```

#### Update Profile
```http
PUT /api/users/profile
Authorization: Bearer <token>
Content-Type: application/json

{
  "username": "newusername",
  "bio": "Learning enthusiast",
  "avatar": "https://example.com/avatar.jpg"
}
```

#### Get User Analytics
```http
GET /api/analytics/user/:userId
Authorization: Bearer <token>
```

### Gamification Endpoints

#### Get Leaderboard
```http
GET /api/gamification/leaderboard?category=all&timeframe=week
Authorization: Bearer <token>
```

#### Get User Achievements
```http
GET /api/gamification/achievements
Authorization: Bearer <token>
```

#### Get Study Streak
```http
GET /api/gamification/streak
Authorization: Bearer <token>
```

### AI Endpoints

#### Generate Questions
```http
POST /api/ai/generate-questions
Authorization: Bearer <token>
Content-Type: application/json

{
  "topic": "React Hooks",
  "difficulty": "medium",
  "count": 10
}
```

#### Get AI Recommendations
```http
GET /api/ai/recommendations
Authorization: Bearer <token>
```

#### Chat with AI Study Buddy
```http
POST /api/ai/study-buddy
Authorization: Bearer <token>
Content-Type: application/json

{
  "message": "Explain closures in JavaScript",
  "context": "learning"
}
```

### Social Endpoints

#### Get Study Groups
```http
GET /api/social/groups
Authorization: Bearer <token>
```

#### Create Study Group
```http
POST /api/social/groups
Authorization: Bearer <token>
Content-Type: application/json

{
  "name": "JavaScript Masters",
  "description": "Learn JS together",
  "category": "programming",
  "isPrivate": false
}
```

#### Add Friend
```http
POST /api/social/friends/:userId
Authorization: Bearer <token>
```

### Real-Time Events (Socket.IO)

#### Join Quiz Room
```javascript
socket.emit('join-quiz-room', { quizId, userId });
```

#### Submit Answer
```javascript
socket.emit('submit-answer', { roomId, questionId, answer });
```

#### Receive Updates
```javascript
socket.on('quiz-update', (data) => {
  console.log('Quiz update:', data);
});
```

---

## 📁 Project Structure

```
EduGameHub/
│
├── backend/
│   ├── algorithms/
│   │   └── spacedRepetition.js      # Spaced repetition algorithm
│   ├── config/
│   │   ├── passport.js               # Passport OAuth config
│   │   └── redis.js                  # Redis configuration
│   ├── controllers/
│   │   ├── activityController.js     # Activity feed logic
│   │   ├── aiQuestionController.js   # AI question generation
│   │   ├── analyticsController.js    # Analytics endpoints
│   │   ├── dashboardController.js    # Dashboard data
│   │   ├── gamificationController.js # Gamification features
│   │   ├── quizController.js         # Quiz CRUD operations
│   │   ├── socialController.js       # Social features
│   │   ├── userController.js         # User management
│   │   └── ...
│   ├── middleware/
│   │   ├── auth.js                   # JWT authentication
│   │   ├── cache.js                  # Redis caching
│   │   ├── rateLimiting.js           # Rate limiting
│   │   └── validation.js             # Input validation
│   ├── models/
│   │   ├── User.js                   # User schema
│   │   ├── Quiz.js                   # Quiz schema
│   │   ├── Report.js                 # Quiz report schema
│   │   ├── StudyGroup.js             # Study group schema
│   │   ├── LearningPath.js           # Learning path schema
│   │   └── ...
│   ├── routes/
│   │   ├── api.js                    # Main API router
│   │   ├── userRoutes.js             # User routes
│   │   ├── quizRoutes.js             # Quiz routes
│   │   ├── analyticsRoutes.js        # Analytics routes
│   │   └── ...
│   ├── services/
│   │   ├── aiQuestionGenerator.js    # AI service
│   │   ├── analyticsService.js       # Analytics logic
│   │   ├── cacheService.js           # Cache management
│   │   └── errorHandler.js           # Error handling
│   ├── tests/
│   │   ├── unit/                     # Unit tests
│   │   └── integration/              # Integration tests
│   ├── utils/
│   │   ├── logger.js                 # Winston logger
│   │   └── responseHelper.js         # API response helper
│   ├── .env                          # Environment variables
│   ├── server.js                     # Entry point
│   └── package.json
│
├── frontend/
│   ├── public/
│   │   ├── manifest.json             # PWA manifest
│   │   ├── sw.js                     # Service worker
│   │   └── assets/                   # Static assets
│   ├── src/
│   │   ├── components/
│   │   │   ├── AIStudyBuddy.jsx      # AI chat component
│   │   │   ├── AdaptiveQuiz.jsx      # Adaptive quiz
│   │   │   ├── AdvancedAnalytics.jsx # Analytics dashboard
│   │   │   ├── EnhancedDashboard.jsx # Main dashboard
│   │   │   ├── GamificationHub.jsx   # Gamification UI
│   │   │   ├── LearningPathHub.jsx   # Learning paths
│   │   │   ├── RealTimeQuiz.jsx      # Multiplayer quiz
│   │   │   ├── StudyGroups.jsx       # Study groups
│   │   │   └── ...
│   │   ├── pages/
│   │   │   ├── Home.jsx              # Landing page
│   │   │   ├── Login.jsx             # Login page
│   │   │   ├── Register.jsx          # Registration
│   │   │   ├── UserQuiz.jsx          # Quiz list
│   │   │   ├── TakeQuiz.jsx          # Quiz taking
│   │   │   ├── UserProfile.jsx       # User profile
│   │   │   ├── Leaderboard.jsx       # Leaderboard
│   │   │   └── ...
│   │   ├── context/
│   │   │   └── ThemeContext.jsx      # Theme management
│   │   ├── hooks/
│   │   │   ├── useKeyboardShortcuts.js
│   │   │   ├── useNetworkStatus.js
│   │   │   └── useNotification.js
│   │   ├── utils/
│   │   │   ├── axios.js              # Axios config
│   │   │   ├── localStorage.js       # Local storage
│   │   │   └── validation.js         # Form validation
│   │   ├── config/
│   │   │   └── config.js             # App configuration
│   │   ├── App.jsx                   # Root component
│   │   ├── main.jsx                  # Entry point
│   │   └── index.css                 # Global styles
│   ├── .env                          # Environment variables
│   ├── vite.config.js                # Vite configuration
│   └── package.json
│
├── .github/
│   └── workflows/
│       ├── basic-checks.yml          # CI pipeline
│       └── security-scan.yml         # Security checks
│
├── docs/
│   └── ADAPTIVE_DIFFICULTY_AND_CONFIDENCE.md
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🚢 Deployment

### Frontend Deployment (Vercel)

1. **Connect Repository**
   ```bash
   # Install Vercel CLI
   npm i -g vercel
   
   # Login and deploy
   cd frontend
   vercel
   ```

2. **Configure Environment Variables**
   - Go to Vercel Dashboard → Settings → Environment Variables
   - Add all variables from `.env`

3. **Build Settings**
   - Build Command: `npm run build`
   - Output Directory: `dist`
   - Install Command: `npm install`

### Backend Deployment (Railway/Render)

1. **Railway Deployment**
   ```bash
   # Install Railway CLI
   npm i -g @railway/cli
   
   # Login and deploy
   cd backend
   railway login
   railway init
   railway up
   ```

2. **Environment Variables**
   - Add all variables from backend `.env`
   - Update `FRONTEND_URL` to your Vercel URL

3. **Database Setup**
   - Use MongoDB Atlas (already configured)
   - Add Redis addon in Railway

### Database Migration

```bash
# Seed learning paths
cd backend
node seedLearningPaths.js

# Run migrations (if any)
node utils/seedLearningPaths.js
```

---

## 🧪 Testing

### Backend Tests

```bash
cd backend

# Run all tests
npm test

# Run with coverage
npm run test:coverage

# Watch mode
npm run test:watch
```

### Frontend Tests

```bash
cd frontend

# Run all tests
npm test

# Watch mode
npm run test:watch

# CI mode
npm run test:ci
```

### Test Coverage

- **Backend**: Controllers, Services, Models, Middleware
- **Frontend**: Components, Utils, Hooks
- **Integration**: API endpoints, Socket.IO events

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/Gaurav822131/EduGameHub.git
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make Changes**
   - Write clean, documented code
   - Follow existing code style
   - Add tests for new features

4. **Commit Changes**
   ```bash
   git commit -m "Add amazing feature"
   ```

5. **Push to Branch**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open Pull Request**
   - Describe your changes
   - Link related issues
   - Wait for review

### Code Style Guidelines

- Use ESLint configuration provided
- Follow React best practices
- Write meaningful commit messages
- Add JSDoc comments for functions
- Keep components small and focused

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Authors

- **Gaurav** - [GitHub](https://github.com/Gaurav822131)

---

## 🙏 Acknowledgments

- Google Gemini AI for intelligent question generation
- MongoDB Atlas for reliable database hosting
- Vercel for seamless frontend deployment
- Socket.IO for real-time communication
- All contributors and supporters

---

## 📞 Support

- **Live Demo**: [edu-gamehub.vercel.app](https://edu-gamehub.vercel.app)
- **GitHub Issues**: [Report a bug](https://github.com/Gaurav822131/EduGameHub/issues)
- **Email**: support@edugamehub.com

---

## 🗺 Roadmap

- [ ] Mobile app (React Native)
- [ ] Video lessons integration
- [ ] Voice-based quizzes
- [ ] AR/VR learning experiences
- [ ] Blockchain certificates
- [ ] Multi-language support
- [ ] Advanced AI tutoring
- [ ] Live video classes

---

<div align="center">

**⭐ Star this repository if you find it helpful!**

Made with ❤️ by the EduGameHub Team

</div>
