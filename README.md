# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

---

# Bumper 🎵

A personal Spotify analytics web app that lets you explore your listening habits — top tracks, top artists, recently played, and what's currently playing.

---

## Features

- 🔐 Spotify OAuth2 login via PKCE (no client secret exposed)
- 🎧 Currently playing track
- 📊 Top tracks and artists (1 month, 6 months, 1 year)
- 🕘 Recently played (last 50 tracks)
- ⏱️ Minutes listened in the last 7 days

---

## Tech Stack

**Frontend**
- React 18
- React Router v7
- React Bootstrap
- Vite

**Auth**
- Spotify Web API
- PKCE Authorization Code Flow

**Deployment**
- Vercel

---

## Getting Started

### Prerequisites

- Node.js 18+
- A Spotify account
- A registered app on the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)

### Installation

```bash
git clone https://github.com/your-username/bumper.git
cd bumper
npm install
```

### Environment Setup

In your Spotify Developer Dashboard:

1. Create an app
2. Add `http://localhost:5173/callback` as a Redirect URI
3. Copy your **Client ID**

Open `src/pages/Login.jsx` and update:

```js
const CLIENT_ID = 'your_client_id_here';
const REDIRECT_URI = 'http://localhost:5173/callback';
```

### Running Locally

```bash
npm run dev
```

Visit `http://localhost:5173`

---

## Deployment (Vercel)

1. Push your repo to GitHub
2. Import the project on [Vercel](https://vercel.com)
3. Add your production redirect URI in the Spotify Dashboard (e.g. `https://your-app.vercel.app/callback`)
4. Update `REDIRECT_URI` in `Login.jsx` to match
5. Ensure a `vercel.json` exists in the project root:

```json
{
  "rewrites": [
    { "source": "/(.*)", "destination": "/index.html" }
  ]
}
```

---

## Spotify Developer Mode

This app is currently in **Spotify development mode**, meaning only manually added users can log in. To request access, contact the developer.

> Extended quota mode (public access) is planned for a future release once a backend is in place.

---

## Roadmap

- [ ] Mobile responsive UI improvements
- [ ] FastAPI backend for secure token exchange and refresh
- [ ] Redis session storage
- [ ] Docker Compose setup (frontend + backend + Redis)
- [ ] Spotify extended quota mode submission

---

## License

MIT
