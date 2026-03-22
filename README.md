# jaybilgaye.github.io

Public profile site for **GitHub Pages**—short, professional, internet-facing.  
Not a full career archive; it highlights how you work and points to Medium, LinkedIn, and GitHub.

## Publish to GitHub Pages

1. On GitHub, create a repository named **`jaybilgaye.github.io`** (must match your username exactly).

2. Push **only the contents of this folder** to the default branch (usually `main`):

   ```bash
   cd jaybilgaye.github.io
   git init
   git add index.html assets/
   git commit -m "Initial profile site"
   git branch -M main
   git remote add origin https://github.com/jaybilgaye/jaybilgaye.github.io.git
   git push -u origin main
   ```

3. In the repo: **Settings → Pages** → Source: **Deploy from a branch** → Branch **`/ (root)`** → Save.

4. After a minute or two, the site is live at **https://jaybilgaye.github.io**

## Customize

- Edit **`index.html`**: bio, pills, featured Medium links, experience one-liners.
- Edit **`assets/style.css`**: colors, max width (`--max`), fonts.

## Pin on GitHub profile

GitHub → **Profile** → **Customize your pins** is for repositories. To show this site, add the URL to your profile **bio** or **social link**, or set **Website** in profile settings to `https://jaybilgaye.github.io`.
