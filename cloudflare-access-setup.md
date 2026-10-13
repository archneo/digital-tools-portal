# Cloudflare Pages + Access wiring

Goal: `tools.trilokventures.org` shows the launcher, but only you can open it.

## 1. Pages
1. GitHub → New repository → `digital-tools-portal` → Private
2. Push this folder
3. Cloudflare Dashboard → Workers & Pages → Create Application → Pages → Connect to Git
4. Pick `archneo/digital-tools-portal`
   - Framework preset: None
   - Build command: (empty)
   - Output directory: `/`
5. Deploy. Note the `*.pages.dev` URL.

## 2. Custom domain
1. Pages project → Custom domains → Set up a custom domain
2. Enter `tools.trilokventures.org` (DNS is already on Cloudflare, so it auto-provisions)

## 3. Zero Trust Access
1. Cloudflare Dashboard → Zero Trust → Access → Applications → Add
2. Type: Self-hosted (or Pages integration), point to `tools.trilokventures.org`
3. Policy: Allow → Emails → your trilokventures.org address
4. Session duration: 24h (good for phone)
5. Test in incognito: should prompt for Google login, then show the launcher

## 4. Phone
Add to home screen from Android Chrome: menu → Add to Home screen. It'll feel like an app.

## Cost
Pages free tier + Access free up to 50 users = $0.

## What NOT to do
- Don't roll your own login form
- Don't put tokens in Pages environment variables for a static launcher (not needed)
- Don't make the GitHub repo public to "simplify" Pages — Pages works fine with private repos
