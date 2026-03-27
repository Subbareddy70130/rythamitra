# RythuMitra - Quick Start Guide

## ✨ Project Overview
RythuMitra is an AI-powered smart agriculture platform that empowers farmers with:
- Crop Recommendations based on soil and weather
- Disease Detection & Solutions
- Marketplace for crop trading
- Weather Advisories
- Learning Resources
- Chatbot Support
- Government Schemes Information

## 🔧 Setup Instructions

### Prerequisites
- Python 3.10+
- Node.js 16+
- MongoDB (local or Atlas)

### Backend Setup

1. **Navigate to backend directory:**
   ```powershell
   cd backend
   ```

2. **Create and activate virtual environment:**
   ```powershell
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   ```

3. **Install dependencies:**
   ```powershell
   pip install -r ..\requirements.txt
   ```

4. **Configure environment variables:**
   - Copy `.env.example` to `.env`
   - Update MongoDB URL and API keys

5. **Run backend (from .vscode Tasks menu):**
   - Open Command Palette (Ctrl+Shift+P)
   - Select "Tasks: Run Task"
   - Choose "Backend: Run (Debug)"

   Or manually:
   ```powershell
   python -m uvicorn app.main:app --reload --host 127.0.0.1 --port 8000
   ```

### Frontend Setup

1. **Navigate to frontend directory:**
   ```powershell
   cd frontend
   npm install
   ```

2. **Run frontend:**
   ```powershell
   npm start
   ```
   Frontend will open at http://localhost:3000

## 🐛 Debugging

### Using VS Code Debug (Recommended)

1. **Backend Debugging:**
   - Open Run & Debug panel (Ctrl+Shift+D)
   - Select "Python: Backend (FastAPI)"
   - Click Run button or press F5
   - Set breakpoints by clicking line numbers

2. **Full Stack Development:**
   - Use compound task to run both services
   - Backend: http://localhost:8000
   - Frontend: http://localhost:3000
   - API Docs: http://localhost:8000/docs

### Common Issues & Fixes

#### Issue: "ModuleNotFoundError: No module named 'uvicorn'"
**Solution:** Ensure virtual environment is activated
```powershell
.\venv\Scripts\Activate.ps1
pip install uvicorn
```

#### Issue: "Registration returns 400 Bad Request"
**Solution:** The fix has been applied to normalize empty strings to None

#### Issue: "MongoDB connection refused"
**Solution:** 
- Ensure MongoDB is running: `mongod`
- Or update MONGODB_URL in .env to your MongoDB Atlas connection string

#### Issue: "OpenWeather API returns 401 Unauthorized"
**Solution:** Add your API key to `.env` file
```
OPENWEATHER_API_KEY=your_actual_key
```

## 📁 Project Structure

```
rythumitra/
├── backend/              # FastAPI application
│   ├── app/
│   │   ├── main.py       # FastAPI app entry point
│   │   ├── routes/       # API endpoints
│   │   ├── services/     # Business logic
│   │   ├── models/       # Pydantic models
│   │   ├── database/     # MongoDB connections
│   │   └── utils/        # Utilities & helpers
│   ├── venv/             # Virtual environment
│   └── requirements.txt   # Python dependencies
├── frontend/             # React application
│   ├── src/
│   │   ├── pages/        # React pages
│   │   ├── components/   # Reusable components
│   │   ├── services/     # API client
│   │   └── styles/       # CSS styles
│   └── package.json      # NPM dependencies
├── .vscode/
│   ├── tasks.json        # Run tasks
│   └── launch.json       # Debug configurations
└── README.md
```

## 🚀 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

### Features
- `GET /api/weather/?city=CityName` - Get weather data
- `GET /api/advisory` - Crop advisory
- `POST /api/disease` - Disease detection
- `GET /api/marketplace` - Marketplace products
- `GET /api/market-prices` - Market prices
- `GET /api/schemes` - Government schemes
- More endpoints available in API docs: http://localhost:8000/docs

## 📊 Development Workflow

1. **Make code changes** in your editor
2. **Automatic reload:** Both backend and frontend support hot reload
3. **Debug:** Use breakpoints in VS Code
4. **Test:** Use Postman or the Swagger UI at http://localhost:8000/docs

## 🛠️ Useful Commands

| Command | Purpose |
|---------|---------|
| `Ctrl+Shift+D` | Open debug panel |
| `F5` | Start debugging |
| `Ctrl+Shift+P` | Open command palette |
| `Tasks: Run Task` | Run predefined tasks |

## 📝 Notes

- Backend runs on `http://localhost:8000`
- Frontend runs on `http://localhost:3000`
- API documentation: `http://localhost:8000/docs`
- Database is MongoDB (default: local, configure in .env)

## 🤝 Support

For issues or questions, check the debug logs in terminal or the global exception handler responses.
