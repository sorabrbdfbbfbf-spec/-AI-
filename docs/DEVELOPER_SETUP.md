# Developer Setup Guide

## Prerequisites

- **Node.js**: v18 or higher
- **npm** or **yarn**: Latest version
- **Git**: For version control
- **Docker** (optional): For running with containers
- **MongoDB** (optional): For persistent data storage

## Installation Steps

### 1. Clone the Repository
```bash
git clone https://github.com/sorabrbdfbbfbf-spec/-AI-.git
cd -AI-
```

### 2. Install Dependencies

**Option A: Using npm (recommended)**
```bash
npm install
```

**Option B: Using Docker Compose**
```bash
docker-compose up --build
```

### 3. Configure Environment Variables

Create a `.env` file in the `backend` directory:

```bash
cp backend/.env.example backend/.env
```

Edit `backend/.env` with your settings:
```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/starchannel-ai
FRONTEND_URL=http://localhost:3000
```

### 4. Start Development Servers

**Option A: Separate Terminals**

Terminal 1 (Backend):
```bash
cd backend
npm install
npm run dev
```

Terminal 2 (Frontend):
```bash
cd frontend
npm install
npm run dev
```

**Option B: Using Concurrently**
```bash
npm run dev
```

**Option C: Using Docker Compose**
```bash
docker-compose up
```

### 5. Access the Application

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000
- **Health Check**: http://localhost:5000/health

## Project Structure

```
-AI-/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── index.html
│   ├── vite.config.js
│   └── package.json
│
├── backend/
│   ├── controllers/
│   │   └── videoController.js
│   ├── routes/
│   │   └── videoRoutes.js
│   ├── server.js
│   ├── .env.example
│   └── package.json
│
├── docs/
│   ├── API.md
│   ├── USER_GUIDE.md
│   └── DEVELOPER_SETUP.md
│
├── docker-compose.yml
├── .gitignore
├── README.md
└── package.json
```

## Development Workflow

### Making Changes

1. Create a new branch:
```bash
git checkout -b feature/your-feature-name
```

2. Make your changes in the appropriate directory

3. Test your changes:
```bash
npm test
```

4. Run linting:
```bash
npm run lint
```

5. Commit your changes:
```bash
git commit -m "feat: Add your feature description"
```

6. Push to your branch:
```bash
git push origin feature/your-feature-name
```

7. Create a Pull Request

### Code Standards

- Follow ESLint rules
- Use meaningful variable and function names
- Add comments for complex logic
- Write tests for new features
- Keep components small and reusable

## Debugging

### Backend Debugging

Use Node's built-in debugger:
```bash
node --inspect server.js
```

Then visit `chrome://inspect` in Chrome.

### Frontend Debugging

- Use React DevTools browser extension
- Use Vue DevTools if switching to Vue
- Open browser console (F12) for JavaScript errors

### Common Issues

**Port Already in Use:**
```bash
# Kill process on port 5000 (backend)
kill -9 $(lsof -t -i:5000)

# Kill process on port 3000 (frontend)
kill -9 $(lsof -t -i:3000)
```

**Dependencies Not Installing:**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

**MongoDB Connection Error:**
Make sure MongoDB is running:
```bash
# Using Docker
docker run -d -p 27017:27017 mongo

# Using Homebrew (macOS)
brew services start mongodb-community
```

## Testing

### Run All Tests
```bash
npm test
```

### Run Frontend Tests
```bash
npm run test:frontend
```

### Run Backend Tests
```bash
npm run test:backend
```

## Building for Production

### Build Frontend
```bash
npm run build:frontend
```

### Build Backend
```bash
npm run build:backend
```

### Docker Build
```bash
docker-compose -f docker-compose.yml build
```

## Additional Resources

- [React Documentation](https://react.dev)
- [Express.js Documentation](https://expressjs.com)
- [Tailwind CSS Documentation](https://tailwindcss.com)
- [MongoDB Documentation](https://docs.mongodb.com)
- [Vite Documentation](https://vitejs.dev)

## Getting Help

- Check existing GitHub Issues
- Review the API Documentation (docs/API.md)
- Create a new issue with detailed information
- Contact the development team

---

Happy coding! 🚀
