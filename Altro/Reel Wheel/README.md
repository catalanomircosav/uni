___
# 🎬 Reel Wheel
A full-stack web application to manage movie nights with friends. Each user submits two movie choices, which are added to a "wheel of fortune" — the last remaining movie is selected for the night. After watching, users rate the film and view their stats over time.

---
## 🚀 Features
- 🎡 Spin the wheel to randomly choose a movie from everyone's picks
- 🔍 Search and add movies using the TMDB API
- 🗳️ Rate movies after each viewing
- 📈 Track your average ratings, watch history, and favorite genres
- 🧠 Simple user dashboard with personal stats
- 🌙 Fully responsive and dark-mode ready

---
## 🧰 Tech Stack
### Frontend
- [React](https://react.dev/) (Vite)
- [Tailwind CSS](https://tailwindcss.com/)
- [React Router](https://reactrouter.com/)
- [Framer Motion](https://www.framer.com/motion/) for animations
- Axios for HTTP requests
### Backend
- [Node.js](https://nodejs.org/) + [Express](https://expressjs.com/)
- [Prisma ORM](https://www.prisma.io/)
- [PostgreSQL](https://www.postgresql.org/) via Docker
- [TMDB API](https://developer.themoviedb.org/) for movie data
---
## 📁 Project Structure
```
cinema-app/
├── frontend/
│ ├── src/
│ ├── components/
│ ├── pages/
│ ├── api/
│ └── ...
│
├── backend/
│ ├── prisma/
│ ├── src/
│ ├── routes/
│ ├── controllers/
│ └── ...
│
├── docker-compose.yml
├── .env
└── README.md
```
___

## 🧪 Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/movie-night-webapp.git
cd movie-night-webapp
```

### 2. Setup the backend
```bash
cd backend
npm install
cp .env.example .env
npx prisma generate
docker-compose up -d
npx prisma migrate dev
npm run dev
```

### 3. Setup the frontend
```bash
cd ../frontend
npm install
npm run dev
```

### 🔑 Environment Variables
Create a .env file in /backend/ with:
```
DATABASE_URL=postgresql://your_user:your_password@localhost:5432/movienight
TMDB_API_KEY=your_tmdb_api_key
```

### 📌 Roadmap
- [ ] Implement spinning wheel UI
- [ ] Add movie to session feature
- [ ] Store and fetch movie ratings
- [ ] User login and dashboard
- [ ] Voting system and rating average
- [ ] Watch history and stats
- [ ] Mobile support


### 🧑‍💻 Contributors
 - catalanomircosav

### 📄 License
MIT License — feel free to use and adapt.
___
