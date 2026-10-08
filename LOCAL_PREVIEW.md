# Preview the website locally

Run the preview from the repository root. You can inspect and edit the website before making any Git commits.

## Docker (available on this machine)

```sh
LOCAL_UID=$(id -u) LOCAL_GID=$(id -g) docker compose up
```

Wait for Jekyll to report that the server is running, then open:

**http://localhost:4000**

Leave the terminal running while editing. Jekyll watches the source files and rebuilds automatically; refresh your browser to see each change. The preview server is accessible only from your machine.

Stop with **Ctrl+C**. Configuration changes require stopping and restarting the server.

If the local image is missing, build it first:

```sh
LOCAL_UID=$(id -u) LOCAL_GID=$(id -g) docker compose up --build
```

The image build installs the Ruby dependencies and needs internet access. Ordinary previews use the installed image. No Node dependency installation is needed for content and style changes.

If port 4000 is already occupied, stop the other server or change the host port in `docker-compose.yaml`, for example to `127.0.0.1:4001:4000`, and open localhost:4001.

## Ruby / Bundler alternative

If you install Ruby and Bundler locally, run once:

```sh
bundle config set --local path vendor/bundle
bundle install
```

Then start the preview:

```sh
bundle exec jekyll serve --host 127.0.0.1 --port 4000 --destination _preview
```

Open **http://localhost:4000**. Stop with **Ctrl+C**. The `_preview/` directory is ignored by Git.

## Review before committing

Check Home, Research, each of the three project pages, Teaching and CV. Open the short CV PDF, click the figures to inspect their full resolution, and try a narrow browser window and both colour themes.

Confirm the scientific descriptions and contribution statements. The PhD schematic is labelled as conceptual; it can be replaced with a manuscript figure later.

Inspect your pending changes:

```sh
git status --short
git diff
```

The Docker preview writes generated files inside the container, leaving the existing tracked `_site/` directory untouched. The new CV and research image directories must be included when you eventually commit the site, since the pages link to those assets.

A local preview does not publish the website. A Git commit records your changes locally; a push to the branch configured for GitHub Pages triggers the site's deployment.
