# Global Chat App

A multi-level chat application where users earn levels by chatting, unlock features, and compete on global and local leaderboards.

## Features

### User System
- User authentication and login
- User profile management
- Level progression system (earn XP by chatting)
- Avatar and customization

### Chat Channels
- **Global Chat**: All users worldwide
- **Continent Chats**: By continent (Africa, Asia, Europe, North America, South America, Australia, Oceania)
- **Country Chats**: By country
- **City Chats**: By city
- **Local Chats**: Nearby users (based on geolocation)
- **Private Chats**: Direct messaging between users

### Leveling System
- XP earned per message (base: 1 XP per message)
- Level thresholds (e.g., 100 XP per level)
- Larger text size at higher levels
- Access to higher-level chat groups (e.g., Level 5+ channels)

### Leaderboards
- Global leaderboard (top users by level/XP)
- Local leaderboard (by country, city, or proximity)
- Time-based leaderboards (weekly, monthly)

### UI Features
- Real-time message updates
- User presence indicators
- Message history
- Search functionality
- Notifications

## Tech Stack

### Backend
- Node.js / Express.js (or Python/FastAPI)
- PostgreSQL or MongoDB (database)
- Socket.io (real-time messaging)
- Redis (caching, session management)
- JWT (authentication)

### Frontend
- React or Vue.js
- Tailwind CSS
- Socket.io client
- Geolocation API
- Real-time updates

### Infrastructure
- Docker
- Docker Compose
- AWS/GCP (deployment)
- Nginx (reverse proxy)

## Project Structure

```
global-chat-app/
├── backend/
│   ├── src/
│   │   ├── models/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── middleware/
│   │   ├── services/
│   │   └── utils/
│   ├── tests/
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── styles/
│   ├── public/
│   └── package.json
├── docker-compose.yml
├── .env.example
└── docs/
```

## Getting Started

### Prerequisites
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL 14+ (or MongoDB 5+)

### Installation

1. Clone the repository
```bash
git clone https://github.com/lex822/global-chat-app.git
cd global-chat-app
```

2. Set up environment variables
```bash
cp .env.example .env
```

3. Start services with Docker Compose
```bash
docker-compose up -d
```

4. Install backend dependencies
```bash
cd backend
npm install
npm run dev
```

5. Install frontend dependencies
```bash
cd frontend
npm install
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user
- `GET /api/auth/me` - Get current user

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update user profile
- `GET /api/users/:id/stats` - Get user stats

### Chat
- `GET /api/chat/messages/:channelId` - Get channel messages
- `POST /api/chat/messages` - Send message
- `GET /api/chat/channels` - List available channels

### Leaderboards
- `GET /api/leaderboard/global` - Global leaderboard
- `GET /api/leaderboard/local/:location` - Local leaderboard
- `GET /api/leaderboard/weekly` - Weekly leaderboard

## WebSocket Events

### Client to Server
- `send_message` - Send a message to a channel
- `join_channel` - Join a chat channel
- `leave_channel` - Leave a chat channel
- `set_location` - Update user location

### Server to Client
- `new_message` - New message in channel
- `user_joined` - User joined channel
- `user_left` - User left channel
- `level_up` - User leveled up
- `leaderboard_update` - Leaderboard changed

## Contributing

Contributions welcome! Please open a PR or issue.

## License

MIT
