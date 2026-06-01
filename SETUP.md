# MagicCast — TikTok approval site (GitHub Pages)

A small static site that gives TikTok everything it needs to approve the app:
- **`index.html`** — the product **landing page** (your app's homepage/website URL).
- **`privacy.html`** — Privacy Policy URL.
- **`terms.html`** — Terms of Service URL.
- **`callback.html`** — the OAuth redirect page (shows your auth code on connect).

All steps are browser-only — no git CLI. Separate from the MagicCast project.

## 1. Create the repo + upload (GitHub web UI)
1. github.com → **New repository**, name it exactly **`<username>.github.io`**, Public, Create.
2. **Add file → Upload files** → drag in **all four** HTML files → Commit.
3. **Settings → Pages** → Deploy from branch **main** / root → Save. Wait ~1 min.

Live URLs:
- Homepage:  `https://<username>.github.io/`
- Privacy:   `https://<username>.github.io/privacy.html`
- Terms:     `https://<username>.github.io/terms.html`
- Callback:  `https://<username>.github.io/callback.html`

## 2. Fill into TikTok for Developers (app `awh0gt8oi1nle0uz`)
- **App / website URL (homepage):** `https://<username>.github.io/`
- **Terms of Service URL:** `https://<username>.github.io/terms.html`
- **Privacy Policy URL:** `https://<username>.github.io/privacy.html`
- **Login Kit → Redirect URI:** `https://<username>.github.io/callback.html`
- **Products:** add **Content Posting API**; **Scopes:** `user.info.basic`,
  `video.upload`, `video.publish`.
- **Verify the URL** (root): meta-tag method — TikTok gives a value → paste it into
  the `<meta name="tiktok-developers-site-verification" content="…">` in **`index.html`**
  → re-upload → Verify. (Or upload TikTok's `.txt` file to the repo root.)

## 3. Point MagicCast at it (on the MASTER)
Settings → Publishing → **TikTok** → **Redirect URI** =
`https://<username>.github.io/callback.html` (exact match). Confirm key/secret. Save.

## 4. Submit for review, then connect
1. Submit the app for review in TikTok (homepage + privacy + terms + scopes are now all set).
2. While unaudited you can still test in **Inbox** mode (or Direct + Private).
3. **Get connect link → approve → copy the code off the callback page → Connect.**
4. **Post last Short to TikTok now** → check your TikTok drafts.

## Then tell me your Pages homepage URL
I'll confirm the connect link + redirect URI line up before you submit/connect.

---
*The Privacy Policy and Terms are accurate templates for this personal tool — read
them and tweak anything that doesn't match how you run it. Not legal advice.*
