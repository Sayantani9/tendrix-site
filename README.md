# TENDRIX — Site

Static single-page site for the TENDRIX bio-inspired tentacle gripper robotic arm (L&T Techgium Hackathon Finalist).

Plain HTML/CSS/JS — no build step, no dependencies.

## Push to GitHub

```bash
cd tendrix-site
git init
git add .
git commit -m "TENDRIX site"
git branch -M main
git remote add origin https://github.com/<your-username>/tendrix-site.git
git push -u origin main
```

## Deploy to Vercel

**Option A — CLI (fastest):**
```bash
npm i -g vercel
cd tendrix-site
vercel --prod
```

**Option B — Dashboard:**
1. Go to https://vercel.com/new
2. Import the `tendrix-site` GitHub repo you just pushed
3. Framework preset: **Other** (static site) — no build command needed
4. Deploy

Either way you'll get a live `https://tendrix-site-<hash>.vercel.app` URL (or set a custom subdomain in Project Settings).
