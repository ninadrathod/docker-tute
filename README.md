# Docker – Complete Tutorial from Scratch

A comprehensive, self-contained HTML tutorial covering every Docker concept from first principles to production-ready usage.

- **12 sections** covering prerequisites through Docker Registry
- **100 MCQ questions** with answers and explanations (in dropdowns)
- **8 SVG diagrams** illustrating key concepts
- **Dark Docker-themed UI** (distinct from the k8s-tute design)
- **Fully offline-capable** (only Google Fonts and Highlight.js load from CDN)

---

## Publishing on GitHub Pages

### Step 1 — Make the Repository Public (Required for Free GitHub Pages)

GitHub Pages is **free for public repositories**. If this repo is private, you have two options:

**Option A (Recommended): Make the repo public**
1. Go to your repo on GitHub → **Settings** → **General**
2. Scroll to the **Danger Zone** section at the bottom
3. Click **"Change repository visibility"** → **"Make public"**
4. Confirm by typing the repo name

**Option B: Use GitHub Pro / Team (keep it private)**  
Paid GitHub plans allow GitHub Pages on private repos. If you have GitHub Pro, Team, or Enterprise Cloud, you can skip making it public.

---

### Step 2 — Push Your Code to GitHub

If you haven't already pushed the `index.html` to GitHub:

```bash
# Navigate to the project directory
cd /Users/ninadrathod/Projects/docker-tute

# Add and commit the files
git add index.html README.md
git commit -m "Add Docker tutorial HTML page"

# Push to GitHub (replace 'main' with your branch name if different)
git push origin main
```

---

### Step 3 — Enable GitHub Pages

1. Go to your repository on **GitHub.com**
2. Click **Settings** (top tab)
3. In the left sidebar, click **Pages** (under "Code and automation")
4. Under **"Build and deployment"** → **Source**, select:
   - **"Deploy from a branch"**
5. Under **Branch**, select:
   - Branch: `main` (or whichever branch has your `index.html`)
   - Folder: `/ (root)`
6. Click **Save**

GitHub will start deploying. Wait 1–3 minutes.

---

### Step 4 — Access Your Live Site

After deployment, your tutorial will be live at:

```
https://<your-github-username>.github.io/<repo-name>/
```

For example:
```
https://ninadrathod.github.io/docker-tute/
```

You can find the exact URL in **Settings → Pages** once deployment completes. GitHub shows a green banner with "Your site is live at https://..."

---

### Step 5 — Update the Site

Any future changes pushed to the `main` branch automatically redeploy GitHub Pages. Just:

```bash
git add index.html
git commit -m "Update tutorial content"
git push origin main
```

Redeployment takes about 1–3 minutes.

---

## Local Preview

To preview locally before publishing:

```bash
# Option 1: Python (built-in, no install needed)
cd /Users/ninadrathod/Projects/docker-tute
python3 -m http.server 8080
# Open: http://localhost:8080

# Option 2: Node.js (if installed)
npx serve .
# Open: http://localhost:3000
```

> **Note:** You can also just open `index.html` directly in your browser (`File → Open`), though some CDN fonts may not load without a server.

---

## Custom Domain Setup (docker-tute.meverse.in)

The `CNAME` file in this repo tells GitHub Pages to serve the site at `docker-tute.meverse.in`.

### DNS Configuration

You need to add a **CNAME record** in your domain registrar / DNS provider for `meverse.in`:

| Type  | Host / Name          | Value                                        | TTL  |
|-------|----------------------|----------------------------------------------|------|
| CNAME | `docker-tute`        | `ninadrathod.github.io`                      | 3600 |

> Replace `ninadrathod` with your actual GitHub username.

After adding the DNS record:
1. Go to **Settings → Pages** in your GitHub repo
2. Under **"Custom domain"**, enter `docker-tute.meverse.in` and click **Save**
3. Check **"Enforce HTTPS"** once the certificate is provisioned (can take up to 24 hours for DNS to propagate)

Once live, your tutorial will be accessible at:
```
https://docker-tute.meverse.in
```

---

## Project Structure

```
docker-tute/
├── index.html   ← The complete tutorial (self-contained)
├── CNAME        ← Custom domain for GitHub Pages
└── README.md    ← This file
```

The tutorial is a **single-file HTML application** — no build step, no framework, no dependencies to install.
