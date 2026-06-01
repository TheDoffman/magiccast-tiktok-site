# MagicCast — TikTok connect site (GitHub Pages)

A tiny static site that serves three things TikTok needs:
- **`index.html`** — the OAuth redirect/callback page (shows your auth code).
- **`privacy.html`** — Privacy Policy (TikTok requires a URL).
- **`terms.html`** — Terms of Service (TikTok requires a URL).

All steps are done in the browser — no git CLI. Separate from the MagicCast project.

## 1. Create the repo (GitHub web UI)
1. github.com → **New repository**.
2. Name it exactly **`<your-username>.github.io`** → serves at root
   `https://<your-username>.github.io/` (easiest to verify with TikTok). Public. Create.
3. **Add file → Upload files** → drag in **all three** files (`index.html`,
   `privacy.html`, `terms.html`) → **Commit**.

## 2. Turn on Pages
Repo → **Settings → Pages** → Deploy from branch **main** / root → Save. Wait ~1 min, then:
- `https://<your-username>.github.io/` → the connect page
- `https://<your-username>.github.io/privacy.html` → Privacy Policy
- `https://<your-username>.github.io/terms.html` → Terms

## 3. Fill these into TikTok for Developers (app `awh0gt8oi1nle0uz`)
- **Terms of Service URL:** `https://<your-username>.github.io/terms.html`
- **Privacy Policy URL:** `https://<your-username>.github.io/privacy.html`
- **Login Kit → Redirect URI:** `https://<your-username>.github.io/`
- **Products:** add **Content Posting API**; **Scopes:** `video.upload`, `video.publish`.
- **Verify the URL/domain** — meta-tag method: TikTok gives a value → paste it into
  the `<meta name="tiktok-developers-site-verification" content="…">` in `index.html`
  → re-upload → Verify. (Or upload the `.txt` file TikTok provides to the repo root.)

## 4. Point MagicCast at it (on the MASTER)
Settings → Publishing → **TikTok** → **Redirect URI** = `https://<your-username>.github.io/`
(exact match). Confirm client key/secret are entered. Save.

## 5. Connect
**Get connect link → approve → copy the code shown on the page → Connect.** Then
mode = **Inbox** → **Post last Short to TikTok now** → check your TikTok drafts.

## Then tell me your Pages URL
I'll confirm the connect link + redirect URI line up before you click through.

---
*Note: the Privacy Policy and Terms are reasonable, accurate templates for this
personal tool — give them a read and tweak anything that doesn't match how you
actually run it. They're not legal advice.*
