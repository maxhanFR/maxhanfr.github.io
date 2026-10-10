# Persian / English Jekyll blog

A minimal editorial blog for GitHub Pages with independent Persian and English posts, RTL/LTR layouts, responsive typography, and a simple language switcher.

## URL structure

- `/` — English homepage
- `/en/` — explicit English homepage
- `/fa/` — Persian homepage
- `/about/` and `/fa/about/` — language-specific About pages
- `/en/<slug>/` and `/fa/<slug>/` — independent articles

Posts are independent: a Persian post does not need an English translation, and vice versa. The home page filters posts by their `lang` front-matter field.

## 1. Create the GitHub repository

For the URL `https://YOUR_USERNAME.github.io/`, create a **public** repository named exactly:

`YOUR_USERNAME.github.io`

Replace `YOUR_USERNAME` in `_config.yml` with your GitHub username.

If you instead use a project repository such as `my-blog`, set `url: "https://YOUR_USERNAME.github.io"` and `baseurl: "/my-blog"` in `_config.yml`, and configure the root index/permalinks as desired.

## 2. Push this project

From this directory:

```bash
git init
git add .
git commit -m "Create bilingual Jekyll blog"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io.git
git push -u origin main
```

If Git says the remote already has commits, first inspect the remote repository and reconcile its contents rather than force-pushing.

## 3. Enable GitHub Pages

Open the repository on GitHub:

1. Go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/(root)`, then save.
4. Wait for the Pages deployment to complete. Your site should be available at `https://YOUR_USERNAME.github.io/`.

GitHub Pages supports Jekyll natively. This starter uses the `github-pages` Gemfile for local preview compatibility. If the repository settings offer GitHub Actions as the publishing source and you prefer an Actions workflow, use GitHub's official Jekyll Pages workflow instead.

## 4. Preview locally (optional)

You need Ruby and Bundler installed. Then run:

```bash
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000/`. If dependency installation fails because your Ruby version is incompatible with the GitHub Pages gem, use a Ruby version supported by the current `github-pages` dependency set.

## 5. Write a post

Create a Markdown file in `_posts/` named with the Jekyll date convention, for example:

`_posts/2026-10-12-fa-azmayesh-ideha.md`

Add front matter:

```yaml
---
layout: post
title: "آزمایش ایده‌ها"
date: 2026-10-12 10:00:00 +0330
lang: fa
dir: rtl
tags: [یادداشت]
excerpt: "خلاصه‌ای کوتاه برای فهرست نوشته‌ها."
permalink: /fa/azmayesh-ideha/
---
متن مقاله را اینجا بنویسید.
```

For English, use `lang: en`, `dir: ltr`, and an `/en/` permalink. The `lang` field is essential because the home page uses it to separate posts. The `dir` field is used by the page layout to set the document direction.

## Notes

- The root page (`/`) is the English homepage; `/en/` is an explicit English route.
- This starter includes `jekyll-feed` and `jekyll-sitemap` through the GitHub Pages plugin bundle.
- Google Fonts are loaded remotely in the CSS. For offline use or stronger privacy, download and self-host the fonts.
- The starter has no JavaScript and no server-side component.
