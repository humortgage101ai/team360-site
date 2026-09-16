# team360.team — marketing site

The public sales page for **Team360**. One file: `index.html`, no build step,
no dependencies. Open it in a browser to work on it.

This is deliberately **not** in the `warriors-app` repo. That repo is the app
itself (`app.team360.team`), and mixing the two meant the sales page rode along
with every app deploy, a second GitHub Action had to exist purely to separate
them again, and `deploy.sh`'s `git add -A` could sweep an unfinished draft into
a release.

## Layout

    public/index.html   the site — everything served
    wrangler.toml       deploy config

Anything outside `public/` is repo furniture and is never served.

## Deploying

Connected to Cloudflare through its Git integration — pushing to `main`
publishes. No GitHub Action, no API token, no secrets to rotate.

Deployed as a **Worker serving static assets**, not as a Pages project.
Cloudflare merged the two flows and its create-an-app wizard now runs
`npx wrangler deploy`, which needs the `wrangler.toml` above; there is no
Worker script, `[assets]` alone serves the directory.

The app is separate, serving `app.team360.team` from the `warriors-app` repo.

## Pricing shown on the page

$15/month per team, $150/year (two months free), and a League tier priced on
request. If these change, they appear in three places: the hero badge, the
pricing cards, and the FAQ.
