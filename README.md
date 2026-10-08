# Jean-Baptiste Himbert — personal website

A Jekyll website hosted on GitHub Pages, using the Academic Pages theme.

## Preview before committing

Docker is already available on this machine. From this repository, run:

```sh
LOCAL_UID=$(id -u) LOCAL_GID=$(id -g) docker compose up
```

Open **http://localhost:4000** in your browser. Jekyll rebuilds when you edit content; refresh the browser to see the changes. Stop with **Ctrl+C**. Restart the command after changing `_config.yml` or `_config_docker.yml`.

The source is mounted read-only. The preview is generated inside the container in `/tmp/jekyll-site`, so previewing does not modify the tracked `_site/` directory. These commands do not commit or publish anything.

If the image has not been built yet, use `docker compose up --build` with the same `LOCAL_UID` and `LOCAL_GID` assignments. See [LOCAL_PREVIEW.md](LOCAL_PREVIEW.md) for the Ruby alternative and a suggested review checklist.

## Editing the site

- `_pages/about.md`: homepage and research statement.
- `_data/research.yml`: the three research cards, shared by Home and Research.
- `_pages/research.html`: Research overview, including a redirect from the old `/portfolio/` URL.
- `_pages/research-*.md`: dedicated project pages.
- `_pages/teaching.md`: teaching and research supervision.
- `_pages/cv.md`: online academic CV.
- `_data/profile.yml`: short CV PDF, optional academic CV PDF, manuscript-status visibility.
- `_data/navigation.yml`: header navigation.
- `_sass/layout/_research.scss`: card and figure styling.

The short CV is linked from `files/CV/`. When a separate academic CV PDF is ready, put it there and set `academic_cv` in `_data/profile.yml`; the download link will appear on the CV page.

Template publications, talks, posts and teaching examples are excluded from the build in `_config.yml`. When the first paper is public, replace the example publication files with the real entry, remove the `_publications` and `_pages/publications.html` exclusions, and add Publications to `_data/navigation.yml`.

## Theme

Based on [Academic Pages](https://github.com/academicpages/academicpages.github.io), a fork of the Minimal Mistakes Jekyll theme. See [LICENSE](LICENSE).
