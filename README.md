# Digital Tools Portal

Private launcher for NJ's daily tools. Static site, deployed to Cloudflare Pages, protected by Cloudflare Access.

## What's inside
- `index.html` — mobile-first launcher page, no build step, no external JS
- `styles.css` — clean, fast styling
- `.gitignore` — blocks secrets from ever being committed
- `SECURITY.md` — ground rules
- `cloudflare-access-setup.md` — wiring guide for Pages + Access + custom domain

## Local preview
Just open `index.html` in a browser. No build needed.

## Deploy (Cloudflare Pages)
1. Create private repo `archneo/digital-tools-portal` on GitHub, push this folder
2. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git
3. Select the private repo, framework preset: None, build command empty, output directory `/`
4. Deploy. You get `*.pages.dev` URL.

Then lock it down with Cloudflare Access (see `cloudflare-access-setup.md`).

## Rules
- Repo stays PRIVATE.
- Never commit `.env`, tokens, API keys, or personal data (addresses, phone numbers).
- All tool links are plain HTTPS URLs. No credentials in the repo, ever.
