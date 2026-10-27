# Poran Chowdury: Portfolio

A fast, static portfolio site: plain HTML, CSS and JavaScript, with no framework and no build step. It uses a dark navy design with glass panels, a code-editor hero, an API request view and architecture diagrams. It works on phones and respects reduced-motion settings.

```
Portfolio/
├── index.html                  page content
├── styles.css                  design (colour tokens at the top)
├── script.js                   sticky nav, scroll fade-in
├── .nojekyll                   tells GitHub Pages to serve files as-is
└── assets/
    ├── favicon.svg
    ├── banner-1920x1080.png        16:9 banner (also the link-preview image)
    ├── banner-source.html          edit this, then re-render the banner
    └── Poran_Chowdury_Resume.pdf   public resume (phone number removed)
```

The previous design is kept in `C:\Users\lenovo\Documents\Portfolio_v1_backup\`.

**Re-render the banner** after editing `banner-source.html`:

```powershell
& "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless=new --hide-scrollbars --window-size=1920,1080 `
  --screenshot="C:\Users\lenovo\Documents\Portfolio\assets\banner-1920x1080.png" `
  "file:///C:/Users/lenovo/Documents/Portfolio/assets/banner-source.html"
```

## Preview locally

Double-click `index.html`, or run a small local server:

```powershell
cd C:\Users\lenovo\Documents\Portfolio
python -m http.server 8000
# open http://localhost:8000
```

## Deploy for free on GitHub Pages (recommended)

Your site will be live at **https://poran-chowdury.github.io**.

1. Sign in to GitHub as **poran-chowdury**.
2. Create a new **public** repository named exactly **`poran-chowdury.github.io`**. Don't add a README.
3. Push this folder:

   ```powershell
   cd C:\Users\lenovo\Documents\Portfolio
   git init
   git add .
   git commit -m "Portfolio site"
   git branch -M main
   git remote add origin https://github.com/poran-chowdury/poran-chowdury.github.io.git
   git push -u origin main
   ```

4. In the repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
5. Wait 1–2 minutes, then open https://poran-chowdury.github.io.

To update the site later, edit the files, then `git add .`, `git commit -m "..."` and `git push`. It redeploys automatically.

## Other free options

| Host | How | Your URL |
| --- | --- | --- |
| **Netlify** | Drag the `Portfolio` folder onto app.netlify.com/drop | `something.netlify.app` |
| **Cloudflare Pages** | Connect the GitHub repo, no build command, output folder `/` | `something.pages.dev` |
| **Vercel** | Import the GitHub repo, framework "Other" | `something.vercel.app` |

**Custom domain (optional, not free):** a domain such as `poranchowdury.dev` costs about USD 10–15 a year. All the hosts above let you attach one for free, with HTTPS included.

## After it's live

- Add the URL to your LinkedIn (Contact info → Website) and to your resume header.
- Pin the portfolio repo on your GitHub profile.
- When you update your resume, regenerate `assets/Poran_Chowdury_Resume.pdf` with the phone number removed, since the site is public.

## Editing tips

- **Colours:** change `--blue`, `--cyan` and `--grad` at the top of `styles.css`.
- **Projects:** each project is one `<article class="card">` in `index.html`. Copy one to add a new project, for example Ledgerly when it ships.
- **Keep it public-safe:** no client internals, no security-incident details, no phone number.
