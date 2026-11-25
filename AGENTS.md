# Repository guidance

## Commands and verification
- Use Bundler: `bundle install`, then `bundle exec jekyll serve --livereload --force_polling`. Polling matters on WSL/Windows-mounted filesystems; restart the server after changing `_config.yml`.
- Verify with `JEKYLL_ENV=production bundle exec jekyll build`; inspect affected pages in `_site/`. There is no configured test, lint, or typecheck suite.
- `Gemfile.lock` pins `github-pages` 233 / Jekyll 3.10.0 and Bundler 4.1.0. Do not assume Jekyll 4 behavior or replace the Pages dependency with standalone Jekyll.
- `.github/workflows/pages.yml` installs locked dependencies with Ruby 3.4 and runs the production build directly; GitHub Pages must use **GitHub Actions**, not branch deployment.

## Site wiring and content
- The site uses custom layouts, not a configured theme: `_layouts/default.html` owns navigation, SEO, and the stylesheet link; `_layouts/post.html` wraps posts in that layout. Styling is in `assets/css/style.css`; there is no frontend asset build.
- Both `index.md` and `blog.md` render `site.posts` and read `post.description`. Add posts as `_posts/YYYY-MM-DD-title.md` with `layout: post`, `title`, and `description`.
- The post eyebrow reads singular `category`, not the README example's `categories`; follow the existing post when setting its display label.
- Post URLs come from `_config.yml`: `/blog/:year/:month/:day/:title/`. Use Liquid's `relative_url` for internal links and assets, as the existing templates do.
- Keep article examples reproducible and free of confidential employer/client information (README requirement).

## Build boundaries
- `_site/` is generated output; `vendor/` and `.bundle/` are ignored local dependencies/configuration. Edit source files, not these directories.
- Keep repository-only documentation in `_config.yml`'s `exclude` list so Jekyll does not publish it.
- `_posts/.gitkeep` preserves the posts directory; the shutdown sample post is intentionally ignored and must not be committed.
