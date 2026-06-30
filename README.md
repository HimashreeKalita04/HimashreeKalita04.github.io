# Himashree Kalita — Portfolio

A Jekyll site hosted on GitHub Pages. Live at **https://himashreekalita04.github.io**

## Push it live (first time)

```bash
cd ~/Documents/job-search/HimashreeKalita04.github.io
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/HimashreeKalita04/HimashreeKalita04.github.io.git
git push -u origin main
```

Then on github.com: **repo → Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save.**
Wait ~1–2 minutes, then open https://himashreekalita04.github.io

> Create the repo first at github.com/new — name it exactly `HimashreeKalita04.github.io`, set it **Public**.

## Update it later

Edit any file, then:
```bash
git add .
git commit -m "what changed"
git push
```
The site rebuilds automatically in ~1 minute. (You can also edit files directly on github.com and commit there — no terminal needed.)

## Add a new case study

1. Copy any file in `_case_studies/` to a new `.md` file.
2. Update the front matter at the top: `title`, `subtitle`, `category` (`fintech` or `consumer`), `order`, `summary`, `meta`.
3. Write the body using the same spine: **Context → Problem → What I did → Impact → What I learned.**
4. Commit & push. It appears on the home page automatically.

## Before going live — TODO

- [ ] In `_config.yml`, replace `linkedin:` with your real LinkedIn URL.
- [ ] Decide whether to round the smallcase figures (₹42 Cr / ₹16 Cr) if they're internal.
- [ ] (Optional) Add a custom domain in Settings → Pages.

## Structure

```
_config.yml          site config (title, linkedin, collections)
index.md             home page (hero + "by the numbers")
about.md             about page
_case_studies/       one .md per case study (auto-listed on home)
_layouts/            HTML templates (default, home, case_study, page)
assets/css/style.css styling
```

## Preview locally (optional)

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```
Requires Ruby + Bundler. Not needed to publish — GitHub builds it for you.
