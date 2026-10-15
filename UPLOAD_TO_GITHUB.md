# Upload this project to GitHub

## Option A: command line (recommended)

1. Create an empty repository on GitHub named `f1-2026-clock` (do **not** tick "Add a README", you already have one).
2. In a terminal, from this project folder:

```bash
git init
git add .
git commit -m "Initial commit: F1 2026 Clock"
git branch -M main
git remote add origin https://github.com/<your-username>/f1-2026-clock.git
git push -u origin main
```

If you use SSH, the remote is `git@github.com:<your-username>/f1-2026-clock.git`.

## Option B: upload in the browser

1. Create the repository on GitHub.
2. Click **uploading an existing file**.
3. Drag in everything from this folder, including the `.github` and `docs` folders (unzip first). Hidden folders such as `.github` need the folder itself dragged in.
4. Write a commit message and click **Commit changes**.

## Turn on the website (GitHub Pages)

1. Open your repository, then **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Open the **Actions** tab and wait for "Deploy to GitHub Pages" to finish (about a minute).
4. Your site is live at `https://<your-username>.github.io/f1-2026-clock/`.

## Finish the repo page

- Add a description and the website URL in the repo's **About** box.
- Add topics such as `formula-1`, `f1`, `countdown`, `html`, `css`, `javascript`, `github-pages`.
- Put your real name in `LICENSE` instead of "F1 2026 Clock contributors" if you want.
- Replace `<your-username>` in `README.md` with your GitHub username.

## Later updates

```bash
git add .
git commit -m "Update standings after Austin GP"
git push
```
