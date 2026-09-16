# team360.team — marketing site

The public sales page for **Team360**. One file: `index.html`, no build step,
no dependencies. Open it in a browser to work on it.

This is deliberately **not** in the `warriors-app` repo. That repo is the app
itself (`app.team360.team`), and mixing the two meant the sales page rode along
with every app deploy, a second GitHub Action had to exist purely to separate
them again, and `deploy.sh`'s `git add -A` could sweep an unfinished draft into
a release.

## Deploying

Connected to Cloudflare Pages via its **Git integration** — pushing to `main`
publishes. No Action, no API token, no secrets to rotate: Cloudflare watches
the repo directly. Build command: none. Output directory: `/`.

The app is a separate Pages project serving `app.team360.team` from the
`warriors-app` repo. Two projects because a Pages project serves one root, so
the sales page and the app cannot both be `/` within one.

## Pricing shown on the page

$15/month per team, $150/year (two months free), and a League tier priced on
request. If these change, they appear in three places: the hero badge, the
pricing cards, and the FAQ.
