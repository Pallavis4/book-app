# Bibliotheque — Book Management System

A React + TypeScript app for managing books (CRUD, search, genre filter) with a **JSON Server** REST API.

## Live links (fill in after deployment)

| Item | URL |
|------|-----|
| **Live app** | `https://YOUR-APP.vercel.app` |
| **GitHub repo** | `https://github.com/YOUR-USERNAME/book-app` |
| **API (Render)** | `https://YOUR-API.onrender.com` |

> Replace the placeholders above, then submit all three on the [assignment form](https://docs.google.com/forms/d/e/1FAIpQLSdOutwnDspdl4Xat8cCA2h6F8HpVz1ji1Sna_nWAE0-zafwww/viewform?usp=publish-editor).

---

## Features

- List books (title, author, genre, publication year)
- Add, edit, delete via REST API
- Search by title or author
- Filter by genre
- Loading states and error handling

## Tech stack

- React 18 + TypeScript + Vite
- JSON Server (mock REST API)

---

## Local setup

### Prerequisites

- [Node.js](https://nodejs.org/) 18 or newer
- npm

### Steps

1. **Clone the repo**

```bash
git clone https://github.com/YOUR-USERNAME/book-app.git
cd book-app
```

2. **Install dependencies**

```bash
npm install
```

3. **Run app + API**

```bash
npm start
```

4. Open **http://localhost:5173**

The dev server proxies `/api` → `http://localhost:3001` (no `.env` needed locally).

### Run separately (optional)

```bash
npm run server   # API → http://localhost:3001
npm run dev      # UI  → http://localhost:5173
```

---

## Environment variables

| Variable | Where | Description |
|----------|--------|-------------|
| `VITE_API_BASE_URL` | Vercel / Netlify | Full API URL, e.g. `https://book-api-xxxx.onrender.com` (no trailing `/`) |

Copy `.env.example` to `.env` only if you want to test production API locally:

```bash
cp .env.example .env
# edit VITE_API_BASE_URL, then: npm run dev
```

---

## Deploy (full stack — required for assignment)

You need **two** deployments: API on **Render**, frontend on **Vercel** (or Netlify).

### Step 1 — Push to GitHub

1. Create a new repository on [GitHub](https://github.com/new) named `book-app` (public, no README).
2. In your project folder:

```powershell
cd "G:\Book Assign\book-app"
git init
git add .
git commit -m "Book Management System - Bibliotheque"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/book-app.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username.

### Step 2 — Deploy API on Render (free)

1. Sign in at [render.com](https://render.com) (GitHub login works).
2. **New +** → **Blueprint** → connect repo `book-app` → Render reads `render.yaml`.
   - Or **New Web Service** → connect repo and set:
     - **Build command:** `npm install`
     - **Start command:** `npm run start:api -- --port $PORT`
3. Wait until status is **Live**.
4. Copy the URL, e.g. `https://book-api-xxxx.onrender.com`.
5. Test in browser: `https://YOUR-API.onrender.com/books` — you should see JSON.

> First request after idle may take ~30s (free tier cold start).

### Step 3 — Deploy frontend on Vercel (free)

1. Sign in at [vercel.com](https://vercel.com) → **Add New** → **Project**.
2. Import your `book-app` GitHub repo.
3. Framework: **Vite** (auto-detected).
4. **Environment variables** → add:

| Name | Value |
|------|--------|
| `VITE_API_BASE_URL` | `https://YOUR-API.onrender.com` |

5. Click **Deploy**.
6. Open the Vercel URL (e.g. `https://book-app.vercel.app`) and test add/edit/delete.

### Alternative — Netlify

1. [app.netlify.com](https://app.netlify.com) → **Add new site** → import repo.
2. Build: `npm run build`, publish: `dist`.
3. **Site settings → Environment variables** → `VITE_API_BASE_URL` = your Render URL.
4. Redeploy.

---

## Verify deployment works

- [ ] Home page loads books
- [ ] Search filters results
- [ ] Genre dropdown works
- [ ] **+ Add Book** saves a new book (refresh — it persists)
- [ ] **Edit** updates a book
- [ ] **Delete** removes a book

If the app loads but API fails, check `VITE_API_BASE_URL` and redeploy Vercel after changing it.

---

## Project structure

```
book-app/
├── db.json                 # API database
├── render.yaml             # Render API deploy config
├── vercel.json             # SPA routing on Vercel
├── src/
│   ├── api/booksApi.ts
│   ├── components/
│   ├── hooks/useBooks.ts
│   └── ...
└── README.md
```

---

## Scripts

| Command | Description |
|---------|-------------|
| `npm start` | API + dev UI together |
| `npm run dev` | Frontend only |
| `npm run server` | JSON Server only |
| `npm run build` | Production build |
| `npm run preview` | Preview production build |

---

## Assignment submission checklist

Submit on the [Google Form](https://docs.google.com/forms/d/e/1FAIpQLSdOutwnDspdl4Xat8cCA2h6F8HpVz1ji1Sna_nWAE0-zafwww/viewform?usp=publish-editor):

- [ ] **GitHub repository link**
- [ ] **Live deployed URL** (Vercel/Netlify — must work with API)
- [ ] **README** (this file — already in the repo)

---

## Author

Your Name — React Assignment
