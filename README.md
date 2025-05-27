# FT_Transcendence

FT_Transcendence is a full-stack real-time social gaming application inspired by the 42 school Transcendence project.  
It provides user authentication (including two-factor), real-time chat, friend management, and a browser-based Pong game.

## Table of Contents

- [Features](#features)  
- [Tech Stack](#tech-stack)  
- [Getting Started](#getting-started)  
  - [Prerequisites](#prerequisites)  
  - [Installation](#installation)  
  - [Running the App](#running-the-app)  
- [Environment Variables](#environment-variables)  
- [Folder Structure](#folder-structure)  
- [Contributing](#contributing)  
- [License](#license)  

## Features

- User registration & login (with optional Two-Factor Authentication via OTP)  
- Persistent sessions & token-based auth (JWT)  
- Real-time WebSocket chat (one-to-one & group)  
- Friend requests & friend lists  
- Browser-based Pong game with matchmaking  
- Leaderboard & statistics tracking  

## Tech Stack

- Backend: Django, Python  
- Frontend: Vanilla JavaScript, HTML, CSS  
- Database: PostgreSQL  
- Caching & Pub/Sub: Redis  
- Real-time: Django Channels (WebSockets)  
- Authentication: JWT, OAuth2  
- Containerization: Docker & Docker Compose  

## Getting Started

### Prerequisites

- Python 3.10+  
- pip  
- Docker & Docker Compose (optional but recommended)  
- PostgreSQL  
- Redis  

### Installation

1. Clone the repository  
   ```bash
   git clone https://github.com/Marouane0107/ft_transcendence.git
   cd ft_transcendence
   ```  
2. Copy and configure environment variables  
   ```bash
   cp backend/.env.example backend/.env
   ```  
   Edit `backend/.env` and set your database URL, Redis URL, JWT secret, OAuth keys, etc.  
3. Install Python dependencies  
   ```bash
   cd backend
   pip install -r requirements.txt
   ```  
4. Run database migrations and collect static files  
   ```bash
   python manage.py migrate
   python manage.py collectstatic --noinput
   ```  

### Running the App

#### With Docker Compose (recommended)

```bash
docker-compose up --build
```

This will start the Django server, PostgreSQL, and Redis services.

#### Locally (without Docker)

1. Ensure PostgreSQL & Redis are running on your machine  
2. In the `backend/` directory, start the Django development server:  
   ```bash
   python manage.py runserver
   ```  
3. Open your browser to `http://localhost:8000`

The frontend assets (HTML/CSS/JS) are served by Django’s static files configuration.

## Environment Variables

Refer to `backend/.env.example` for a full list. Common variables include:

- DATABASE_URL  
- REDIS_URL  
- JWT_SECRET  
- GOOGLE_CLIENT_ID / GOOGLE_CLIENT_SECRET (for OAuth)  
- ALLOWED_HOSTS  

## Folder Structure

```
ft_transcendence/
├── backend/          # Django project and apps
│   ├── manage.py
│   ├── requirements.txt
│   ├── .env.example
│   └── <apps>/       # Your Django apps
├── docker-compose.yml
└── README.md
```

## Contributing

1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/YourFeature`)  
3. Commit your changes (`git commit -m "feat: add YourFeature"`)  
4. Push to the branch (`git push origin feature/YourFeature`)  
5. Open a Pull Request  

Please adhere to the existing code style and include tests where applicable.

## License

