# Bless the Mess — website

A free, self-managed website for Bless the Mess (@bless.themess30).
The site is hosted on **Netlify**, the files live on **GitHub**, and Muskan updates
everything from a private admin page at `/admin`. No coding is needed after setup.

## What's in this folder

| Path | What it is |
|---|---|
| `index.html` | The website |
| `data/artworks.json` | Every artwork: title, category, price, photo, Instagram post link |
| `data/site.json` | Banner text, About section, delivery note, category prices |
| `images/` | Artwork photos and the signature logo (`images/uploads` holds new uploads) |
| `admin/` | The private "Manage artworks" page |
| `netlify.toml` | Hosting settings |

## Going live (one time, about 30 minutes)

### 1. Put the files on GitHub
1. Create a free account at github.com (Muskan's own account is best, so the site is hers).
2. Click **New repository**, name it `blessthemess`, and create it.
3. On the new repository page, click **uploading an existing file**, then drag in **everything inside this folder**
   (so `index.html` sits at the top level, not inside another folder). Click **Commit changes**.
4. (Already done: `admin/config.yml` points to Muskaanmm/Blessthemess.)

### 2. Publish it on Netlify
1. Go to netlify.com and sign up **with GitHub**.
2. **Add new project → Import an existing project → GitHub**, pick `blessthemess`, and deploy
   (no build command is needed).
3. In **Project configuration**, change the project name to `blessthemess`. The site is now at
   `https://blessthemess.netlify.app`.
   If that name is taken, pick another and update `site_url` in `admin/config.yml` to match.

### 3. Switch on the admin login
1. On GitHub: **Settings → Developer settings → OAuth Apps → New OAuth App**.
   - Application name: `Bless the Mess admin`
   - Homepage URL: `https://blessthemess.netlify.app`
   - Authorization callback URL: `https://api.netlify.com/auth/done`
   Register it, then **Generate a new client secret**. Copy the Client ID and the secret.
2. On Netlify: **Project configuration → Security → OAuth → Install provider → GitHub**,
   paste the Client ID and secret, and save.
3. If the repository is under someone else's GitHub account, add Muskan's account under
   the repository's **Settings → Collaborators** so she can log in.

## Everyday use (for Muskan)

Go to `https://blessthemess.netlify.app/admin` and log in with GitHub.

- **Add a new artwork:** Artworks → All artworks → **Add artwork** (it appears at the top).
  Upload the photo, fill in the title, category and price, paste the Instagram post link,
  then click **Publish**. The site updates within a minute or two.
- **Get a post's link:** open the post on Instagram, tap ••• (or the share icon) → **Copy link**.
- **Change a price or mark something sold:** open the artwork, edit, Publish.
- **Write the About section:** Site text & prices → **About — a few lines from you**.
- **Category price ranges** ("What I make"): Site text & prices → Categories.
- **Featured originals:** tick "Show in Featured originals" on up to 3 artworks.

Empty prices show "Ask for price". Artworks without a post link open her Instagram profile.

## Optional: your own domain
A custom address (e.g. `blessthemess.in`) can be bought from any domain seller and connected in
Netlify under **Domain management**. This is the only part that costs money; the rest is free.
