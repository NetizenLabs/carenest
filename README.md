# CareNest site — deploy steps (5 minutes, $0)

Static site, no build step. Folder contents ARE the site root:
- `/` — brand home
- `/emergency-care-sheet/` — the Pinterest landing page (all 15 test Pins point here)
- `/downloads/CareNest-Emergency-Care-Sheet.pdf` — the free lead printable
- `/assets/` — logo + PDF page previews

## Deploy on Vercel (recommended)
1. Go to vercel.com/new and drag in the `carenest-site.zip` (or push this folder to GitHub and import the repo). Framework preset: **Other**. No build command, no output directory.
2. After it deploys, open Project → Settings → Domains → add `carenest.abusufyan.xyz`.
3. Where abusufyan.xyz DNS is managed, add the record Vercel shows (usually: CNAME, host `carenest`, value `cname.vercel-dns.com`). Wait for the domain to show "Valid Configuration".
4. Tell Kimi it's live → Kimi adds the website to the Pinterest profile and submits the Pinterest claim.

## After deploy — 2 one-time checks
- **Test the form once with your own email.** The first submission triggers a one-time FormSubmit activation email to safyan223242@gmail.com — click "Activate" in it. After that, every signup lands in that inbox silently, and the download link appears instantly for the visitor either way.
- **Pinterest claim:** in Pinterest Settings → Claim, claim `carenest.abusufyan.xyz`. If Pinterest gives a meta tag, paste it where marked in `emergency-care-sheet/index.html` (comment near the top) and redeploy; a DNS TXT record works too.

## Notes
- GA4: placeholder comment in the landing page head — add the tag once a GA4 property exists (needed before any Journey by Mediavine application).
- Email capture endpoint lives in the `<script>` at the bottom of `emergency-care-sheet/index.html` (FormSubmit AJAX to safyan223242@gmail.com). Swap it there if you move to another provider later.
