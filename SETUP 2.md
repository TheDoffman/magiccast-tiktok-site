# TikTok redirect page — GitHub Pages setup (no git CLI needed)

This tiny site is ONLY the OAuth redirect target for connecting TikTok. It's
separate from the MagicCast project. Everything below is done in the browser.

## 1. Create the repo (GitHub web UI)
1. Sign in at github.com → **New repository**.
2. Name it exactly **`<your-username>.github.io`** (a "user site" → serves at the
   clean root `https://<your-username>.github.io/`, which is the easiest URL to
   verify with TikTok). Public. Create.
3. On the repo page: **Add file → Upload files** → drag in **`index.html`** from
   this folder → **Commit changes**.

## 2. Turn on Pages
1. Repo → **Settings → Pages**.
2. Source = **Deploy from a branch**, branch = **main**, folder = **/ (root)** → Save.
3. Wait ~1 min, then open **`https://<your-username>.github.io/`** — you should see
   the "MagicCast — TikTok connect" page (it'll say "No code in the URL yet" — correct).

## 3. Register + verify the URL in TikTok
1. TikTok for Developers → your app (**client key `awh0gt8oi1nle0uz`**) → **Login Kit**.
2. Add **Redirect URI**: `https://<your-username>.github.io/`
3. TikTok will make you **verify the domain/URL**. Pick the **meta-tag** method if
   offered: it gives you a value → paste it into the `content="..."` of the
   `<meta name="tiktok-developers-site-verification" ...>` tag in `index.html` →
   re-upload the file → click **Verify**.
   - If TikTok instead gives a **.txt file**: upload that file to the repo root
     (Add file → Upload files) and use the file method.
4. Make sure the app has the **Content Posting API** product added, scopes
   **`video.upload`** + **`video.publish`**.

## 4. Point MagicCast at it (on the MASTER)
1. MagicCast → Settings → Publishing → **TikTok**.
2. **Redirect URI** field → `https://<your-username>.github.io/` (must match step 3 EXACTLY).
3. Confirm Client key / Client secret are entered. Save.

## 5. Connect
1. **Get connect link** → approve in the browser.
2. TikTok bounces to your Pages URL → the page shows your **code** with a Copy button.
3. Paste it into the **Connect** box → **Connect**. Status → "Connected ✓".
4. Mode = **Inbox** → **Post last Short to TikTok now** → check your TikTok drafts.

## Then tell me
Once your Pages URL is live, tell me the exact URL and I'll confirm the connect
link + redirect URI line up before you click through.
