# Amazon Product Tracker

**Live Website:** [https://amazonprice-tracker.vercel.app/]

## Purpose

This project is a web application for tracking Amazon product prices. It allows users to monitor product prices over time, view price history, and get notified when prices drop. The application includes a web scraper that periodically fetches product data from Amazon.

## Tech Stack

### Backend
- **Python** - Primary language
- **FastAPI** - Modern, fast web framework for building APIs
- **SQLAlchemy** - SQL toolkit and ORM
- **PostgreSQL** - Database for storing product and price data
- **Playwright** - Browser automation for web scraping
- **Redis** - Caching and task queue
- **BeautifulSoup4** - HTML parsing
- **Pydantic** - Data validation

### Frontend
- **React 18** - UI library
- **TypeScript** - Type safety
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Material UI (MUI)** - React component library
- **Radix UI** - Headless UI components
- **Axios** - HTTP client
- **Lucide React** - Icon library
- **Recharts** - Charting library

## Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+
- PostgreSQL
- Redis

### Backend Setup

```bash
cd amz_backend

# Create virtual environment
python -m venv .venv

# Activate virtual environment
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
# OR using uv:
uv pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your database and Redis credentials

# Run database migrations
# (Add your migration command here)

# Start the server
uvicorn main:app
```

The backend API will be available at `http://localhost:8000`

### Frontend Setup

```bash
cd amz_frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

The frontend will be available at `http://localhost:5173`

## Environment Variables

### Backend (.env)
```
DATABASE_URL=postgresql://user:password@localhost:5432/amz_db
REDIS_URL=redis://localhost:6379
SECRET_KEY=your-secret-key
```

## Project Structure

```
amz_monorepo/
├── amz_backend/          # FastAPI backend
│   ├── main.py          # Application entry point
│   ├── routes.py        # API routes
│   ├── models.py        # Database models
│   ├── scrape_script.py # Web scraper
│   └── ...
└── amz_frontend/        # React frontend
    ├── src/            # Source code
    ├── index.html      # HTML entry point
    └── ...
```

## Development

### Running the Full Stack

1. Start PostgreSQL and Redis servers
2. Start the backend: `cd amz_backend && uvicorn main:app --reload`
3. Start the frontend: `cd amz_frontend && npm run dev`
