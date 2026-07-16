# Deploy to GitHub Pages (one-time)

Your archive is already a git repo at:

`/Users/didi/Desktop/Work/外卖/AI/Newsletter/site`

## Option A — Terminal (recommended)

### 1. Log in to GitHub CLI

```bash
export PATH="$HOME/.local/bin:$PATH"
gh auth login
```

Choose: **GitHub.com** → **HTTPS** → **Login with a web browser** (or paste a Personal Access Token).

### 2. Create the repo + enable Pages

```bash
cd "/Users/didi/Desktop/Work/外卖/AI/Newsletter/site"
export PATH="$HOME/.local/bin:$PATH"

gh repo create food-delivery-weekly-digest --public --source=. --remote=origin --push

gh pages enable --repo "$(gh repo view --json nameWithOwner -q .nameWithOwner)" --branch main --build-type legacy --path /
# If `gh pages enable` is unavailable on your CLI version, use the browser:
# Repo → Settings → Pages → Branch: main → Folder: / (root) → Save
```

### 3. Your public link

After 1–2 minutes:

`https://<your-username>.github.io/food-delivery-weekly-digest/`

---

## Option B — Browser only

1. Open [https://github.com/new](https://github.com/new)
2. Name: `food-delivery-weekly-digest` · Public · **no** README
3. On your Mac:

```bash
cd "/Users/didi/Desktop/Work/外卖/AI/Newsletter/site"
git remote add origin https://github.com/<YOUR_USERNAME>/food-delivery-weekly-digest.git
git push -u origin main
```

4. Repo → **Settings** → **Pages** → Source: **Deploy from a branch** → Branch **main** → Folder **/ (root)** → Save

---

## Later weeks

After Week 29 files are added and committed:

```bash
cd "/Users/didi/Desktop/Work/外卖/AI/Newsletter/site"
git add weeks/2026-w29.html data/weeks.json
git commit -m "Add Week 29 digest"
git push
```

Same URL; history accumulates automatically.
