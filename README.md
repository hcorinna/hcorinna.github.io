# hcorinna.github.io

Source of [hcorinna.github.io](https://hcorinna.github.io), Corinna Hertweck's personal website.
Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme,
deployed to the `gh-pages` branch by [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) on every push to `main`.

## Where things live

| Content | File(s) |
|---|---|
| About page | `_pages/about.md` |
| Publications page | `_pages/publications.md` (which years are listed is set in its front matter) |
| Bibliographies | `_bibliography/{conferences,journals,workshops,preprints,thesis}.bib` |
| News items | `_news/*.md` (`date:` in the front matter controls the order) |
| CV | `assets/pdf/cv.pdf` (`/cv/` redirects there) |
| Imprint | `_pages/imprint.md` |
| Site settings, social links | `_config.yml` |

## Local preview

Requires a current Ruby (≥ 3.x) and ImageMagick, e.g. via Homebrew: `brew install ruby imagemagick`.

```sh
export PATH="/usr/local/opt/ruby/bin:$PATH"   # Homebrew Ruby (Intel Mac; /opt/homebrew/opt/ruby/bin on Apple Silicon)
export LC_ALL=en_US.UTF-8                      # bibtex parsing fails under a non-UTF-8 locale
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve                       # http://localhost:4000
```

Changes to `_config.yml` require restarting `jekyll serve`.
