# Airbnb Clone

A full-stack web application built with Node.js, Express, MongoDB, and EJS. This project allows users to browse, book, and manage vacation rentals.

## Features

- User authentication (Login/Signup)
- Browse available homes
- Book homes as a guest
- Host homes as a property owner
- Favorite homes
- Upload home images
- Real-time session management
- Responsive design with Tailwind CSS

## Prerequisites

- **Node.js** (v16+)
- **MongoDB** (Community Edition)
- **npm**

## Installation

### 1. Install MongoDB

**Windows (using winget):**
```bash
winget install MongoDB.Server
```

**Or download from:** [mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)

### 2. Create MongoDB Data Directory

```powershell
New-Item -ItemType Directory -Path C:\data\db -Force
```

### 3. Clone or Navigate to Project

```bash
cd path/to/airbnb
```

### 4. Install Dependencies

```bash
npm install
```

### 5. Configure Environment Variables

Create a `.env` file in the root directory (copy from `.env.example`):

```bash
MONGODB_URI=mongodb://localhost:27017/airbnb
SESSION_SECRET=your-secret-key-here
PORT=3003
NODE_ENV=development
```

## Running the Project

### Terminal 1: Start MongoDB

```powershell
& "C:\Program Files\MongoDB\Server\8.2\bin\mongod.exe"
```

### Terminal 2: Start the Application

```bash
npm start
```

This will:
- Start the Express server on `http://localhost:3003`
- Start Tailwind CSS in watch mode
- Watch for file changes with nodemon

## Access the Application

Open your browser and navigate to:
```
http://localhost:3003
```

## Project Structure

```
├── app.js                 # Main server file
├── controllers/           # Route handlers
├── models/               # Database models
├── routes/               # API routes
├── views/                # EJS templates
├── public/               # Static files (CSS, images)
├── uploads/              # User-uploaded images
├── utils/                # Utility functions
├── package.json          # Dependencies
├── nodemon.json          # Auto-reload config
├── tailwind.config.js    # Tailwind CSS config
└── .env                  # Environment variables (local)
```

## Available Routes

- `GET /` - Home page
- `GET /login` - Login page
- `POST /login` - Submit login
- `GET /signup` - Signup page
- `POST /signup` - Submit signup
- `GET /homes` - Browse all homes
- `GET /homes/:id` - View home details
- `GET /host` - Host dashboard
- `POST /host/add-home` - Add new home
- `POST /host/edit/:id` - Edit home
- `POST /reserve` - Reserve a home

## Technologies Used

- **Backend:** Node.js, Express.js
- **Database:** MongoDB, Mongoose
- **Frontend:** EJS, Tailwind CSS, HTML5
- **Authentication:** bcryptjs, express-session
- **File Upload:** Multer
- **Validation:** express-validator
- **Auto-reload:** Nodemon

## Security Notes

⚠️ **Production Deployment:**
- Change `SESSION_SECRET` in `.env` to a strong random string
- Use MongoDB Atlas or managed MongoDB for production
- Set `NODE_ENV=production`
- Use HTTPS
- Add proper error handling and logging
- Implement rate limiting
- Sanitize user inputs

## Development

- Automatic CSS compilation with Tailwind
- Hot-reload with Nodemon
- Use `npm start` to run both server and CSS compiler

## Troubleshooting

**Port Already in Use:**
```powershell
netstat -ano | findstr :3003
taskkill /PID <PID> /F
```

**MongoDB Connection Error:**
- Ensure MongoDB server is running
- Check `MONGODB_URI` in `.env`

**Upload Issues:**
- Ensure `uploads/` directory exists
- Check file permissions

## License

ISC

## Author

Your Name
