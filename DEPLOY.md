# Quick deploy guide (copy-paste)

Do these in order. Total time: ~15–20 minutes.

## 1. GitHub

```powershell
cd "G:\Book Assign\book-app"
git init
git add .
git commit -m "Bibliotheque Book Management System"
git branch -M main
```

Create repo at https://github.com/new → name: `book-app` → Create (empty).

```powershell
git remote add origin https://github.com/YOUR_USERNAME/book-app.git
git push -u origin main
```

**Your GitHub link:** `https://github.com/YOUR_USERNAME/book-app`

---

## 2. Render (API)

1. https://dashboard.render.com → **New** → **Blueprint**
2. Connect GitHub → select `book-app`
3. Apply blueprint → wait for **Live**
4. Open service URL → add `/books` to test

**Your API URL:** `https://book-api-xxxx.onrender.com`

---

## 3. Vercel (website)

1. https://vercel.com/new → Import `book-app`
2. **Environment Variables:**
   - `VITE_API_BASE_URL` = `https://book-api-xxxx.onrender.com`
3. Deploy → open site URL

**Your live URL:** `https://book-app.vercel.app` (or similar)

---

## 4. Update README

Edit `README.md` table at the top with your real GitHub, Vercel, and Render URLs, then:

```powershell
git add README.md
git commit -m "Add live deployment URLs"
git push
```

---

## 5. Submit form

https://docs.google.com/forms/d/e/1FAIpQLSdOutwnDspdl4Xat8cCA2h6F8HpVz1ji1Sna_nWAE0-zafwww/viewform?usp=publish-editor

Paste:

- GitHub repo link  
- Live Vercel URL  
- Mention README is in the repo  
