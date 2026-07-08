# 🎓 E-Learning Platform

A full-stack e-learning platform built with Next.js, Node.js, Express, and MongoDB. Features course creation, video streaming, progress tracking, role-based access control, and certificate generation.

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js (App Router) + Tailwind CSS |
| Backend | Node.js + Express.js |
| Database | MongoDB (Mongoose ODM) |
| Auth | JWT + bcrypt (Secured via sessionStorage to prevent tab-sharing) |
| Video Storage | Cloudinary |
| State Management| React Context API |

## ✨ Currently Working Features

### 🧑‍🎓 Student Experience
- **Secure Authentication**: Register and login securely. Tokens are isolated per tab.
- **Course Enrollment**: Browse available published courses and enroll.
- **Video Learning**: Watch video lessons via integrated Cloudinary video player.
- **Progress Tracking**: System tracks playback position and completed lessons. Resume exactly where you left off.
- **Certificates**: Automatically issue and download PDF certificates upon 100% course completion. Verify certificates publicly.

### 🧑‍🏫 Teacher Experience
- **Dashboard**: Overview of created courses and student enrollments.
- **Course Builder**: Create and edit courses (Title, Description, Thumbnail, Category).
- **Curriculum Management**: Add sections and individual video lessons.
- **Video Uploads**: Direct integration with Cloudinary for robust video hosting.
- **Publishing**: Keep courses as drafts while editing, and publish when ready.

### 🛡️ Admin Controls
- **Admin Dashboard**: View platform-wide statistics (total users, active teachers, published courses).
- **User Management**: Approve teacher accounts, delete users.
- **Course Management**: Monitor all courses and delete inappropriate content.

### 🔒 Security Features
- **Strict Role-Based Access Control**: `ProtectedRoute` guards ensuring Students cannot access Teacher tools, and non-Admins cannot view Admin pages.
- **Tab Isolation**: Tokens are strictly held in `sessionStorage`. Copying a link to a new tab requires a fresh login, protecting against session hijacking via unattended devices.
- **API Protection**: Backend routes verify JWTs and specific user roles before processing data.

## 📁 Project Structure

```
E-Learning Platform/
├── backend/
│   ├── src/
│   │   ├── models/          # User, Course, Enrollment, Certificate
│   │   ├── routes/          # API endpoints (Auth, Courses, Admin, Upload)
│   │   ├── middleware/      # JWT Auth & Role guards
│   │   └── utils/           # Helper functions
│   ├── server.js            # Express Entry Point
│   └── .env                 # Environment Config
│
└── frontend/
    ├── src/
    │   ├── app/             # Next.js App Router (Pages & Layouts)
    │   ├── components/      # Reusable UI Components
    │   └── context/         # Auth & Theme Contexts
    └── tailwind.config.js
```

## 🚀 Getting Started

### Prerequisites
- Node.js v16+
- MongoDB (local or cloud)
- Cloudinary Account

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
npm install
```

2. Create a `.env` file:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/elearning
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
NODE_ENV=development
```

3. Start the server:
```bash
npm run dev
```

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
npm install
```

2. Start the development server:
```bash
npm run dev
```

The frontend will be available at `http://localhost:3000`.

## 🤝 Contributing

1. Create a feature branch: `git checkout -b feature/your-feature`
2. Commit changes: `git commit -am 'Add feature'`
3. Push to branch: `git push origin feature/your-feature`
4. Submit a pull request
