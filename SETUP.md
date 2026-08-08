# Setup Guide

## Folder structure

```
YOUR_USERNAME/                      ← repo must be named exactly your username
├── README.md                       ← renders as your GitHub profile page
├── SETUP.md                        ← this file (optional, safe to delete after setup)
└── .github/
    └── workflows/
        └── snake.yml                ← auto-generates the animated contribution snake
```

## Step 1 — Create the special profile repo

1. On GitHub, create a **new public repository** named exactly the same as your username
   (e.g. if your username is `MariaStalinRaj`, the repo must be `MariaStalinRaj/MariaStalinRaj`).
2. Check **"Add a README file"** or just push this folder's contents directly.

## Step 2 — Double-check the username-dependent links

The username `gautammanak1` is already filled in throughout `README.md` (stats card,
top languages, streak stats, activity graph, snake animation, trophies, profile-view
counter). If your GitHub username is ever different, search-and-replace
`gautammanak1` with the correct one everywhere it appears.

The **Organizations** section links to `fetchai`, `kloudidev`, and `MeerutCodeHub` —
update or remove those if they don't match your actual org memberships.

## Step 3 — Push the files

```bash
git init
git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.git
git add .
git commit -m "Set up profile README and contribution snake"
git branch -M main
git push -u origin main
```

## Step 4 — Let the snake workflow run

The workflow in `.github/workflows/snake.yml` runs automatically once a day (and on every
push to `main`). It:
1. Reads your public contribution graph
2. Renders it as an animated "snake" that eats the contribution squares
3. Publishes the generated SVG/GIF files to a branch called `output`

No secrets need to be added manually — it uses the repo's built-in `GITHUB_TOKEN`.
The first run may take a minute or two after your first push; you can also trigger it
manually from the **Actions** tab using **"Run workflow"**.

If it doesn't push successfully, go to **Settings → Actions → General → Workflow
permissions** in your repo and make sure **"Read and write permissions"** is selected —
GitHub sets new repos to read-only for Actions by default.

## Step 5 — Verify

Once the `output` branch exists and contains `github-contribution-grid-snake-dark.svg`,
the snake image in your README will start rendering automatically — no further action
needed. It refreshes daily on its own.
