# Security ground rules

1. This repo is PRIVATE. Do not make it public.
2. Never commit credentials, tokens, API keys, or personal data (addresses, phone numbers).
3. Tool tiles link to public login pages only. Authentication happens on the provider's site, not here.
4. No custom auth code in this repo. Remote access is enforced by Cloudflare Access (Zero Trust), not by app logic.
5. If a secret is ever committed by mistake: revoke it immediately, purge from git history, and rotate.

Cloudflare Access policy: Allow only your Google Workspace identity (trilokventures.org). No service tokens in the repo.
