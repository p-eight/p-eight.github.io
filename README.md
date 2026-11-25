# Pedro Bonifácio — Technical Blog

Personal website and technical blog built with Jekyll and hosted on GitHub Pages.

The blog covers C++, Windows internals, debugging, concurrency, secure communication, and systems engineering.

**Website:** https://p-eight.github.io/  
**Repository:** https://github.com/p-eight/p-eight.github.io

## Requirements

- Ruby
- Bundler
- Git

## Local Development

Clone the repository:

```bash
git clone https://github.com/p-eight/p-eight.github.io.git
cd p-eight.github.io
```

Install dependencies:

```bash
bundle install
```

Start the development server:

```bash
bundle exec jekyll serve --livereload --force_polling
```

Open http://localhost:4000/ in your browser.

The `--force_polling` option is useful when running Jekyll through WSL on a Windows-mounted filesystem.

Changes to Markdown, HTML, and CSS are rebuilt automatically. Changes to `_config.yml` require restarting Jekyll.

## Production Build

Generate the static website locally:

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

The output is generated in `_site/`.

## Writing Articles

Create a new Markdown file under `_posts/` using the format:

`YYYY-MM-DD-article-title.md`

Example:

`2026-11-24-debugging-windows-services.md`

Include YAML front matter:

```yaml
---
layout: post
title: "Debugging Windows Services"
date: 2026-11-24
description: "Investigating shutdown failures and blocked worker threads."
categories: [cpp, windows, debugging]
---
```

Articles are generated automatically by Jekyll and made available through the blog.

## Deployment

The website is hosted on GitHub Pages.

Repository: `p-eight/p-eight.github.io`

Production URL: https://p-eight.github.io/

To configure deployment:

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment → Source**, select **GitHub Actions**.

The workflow in `.github/workflows/pages.yml` builds with Ruby 3.4 and the
dependencies in `Gemfile.lock`, then publishes the website on pushes to `main`.
It can also be run manually with **Run workflow**.

## Project Structure

```text
.
├── _config.yml
├── _layouts/
├── _posts/
├── assets/
├── about.md
├── blog.md
├── index.md
├── projects.md
├── Gemfile
└── README.md
```

## Notes

- `_site/` contains generated website output and is not committed.
- `vendor/` contains locally installed Ruby dependencies and is not committed.
- Technical articles should use reproducible examples and avoid confidential employer or client information.

## License

No license has been specified for this repository.
