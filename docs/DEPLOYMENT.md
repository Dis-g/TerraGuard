# Deployment Guide

## 1. Deployment Status

TerraGuard is currently configured for local development.

The frontend has not yet been deployed to Vercel, and the
backend has not yet been deployed to a production hosting service.

The intended deployment architecture is:

- Frontend: Vercel
- Backend: FastAPI hosted separately
- Model artifacts: Included in the backend deployment
- Historical inventory: Included in the backend deployment
- External weather data: Open-Meteo APIs

Vercel will serve the React frontend. It will not host the
FastAPI application as a continuously running Python service
in this architecture.

## 2. Prerequisites

- Python 3.10 or later
- Node.js 18 or later
- npm
- Git
- Internet connectivity

## 3. Local Backend Setup

From the project root:

```bash
cd backend

python -m venv .venv

# Windows
.venv\Scripts\activate

# Linux/macOS
source .venv/bin/activate

pip install -r requirements.txt