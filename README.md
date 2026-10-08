# YourGP Start Page

A browser start page for YourGP staff. Pick your role on the left and the links change to match.

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole page. Links, announcements and search all live in here. |
| `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png` | The teal Y icon for browser tabs and phone home screens. |
| `robots.txt` | Asks Google and other search engines not to list the page. |

## Put it on GitHub Pages (one-off, about 10 minutes)

1. **Sign in to GitHub.** Use the YourGP account or organisation if there is one, so the page doesn't depend on one person's login.
2. **Create a new repository.** Click **+** (top right), then **New repository**.
   - Name: `start` (or anything you like; it becomes part of the address)
   - Visibility: **Private** (your paid plan allows Pages from a private repo, so the code stays hidden)
   - Click **Create repository**
3. **Upload the files.** On the new repo page, click **uploading an existing file**. Drag in everything from this folder. Click **Commit changes**.
4. **Turn on Pages.** Go to **Settings** > **Pages**.
   - Source: **Deploy from a branch**
   - Branch: **main**, folder **/ (root)**
   - Click **Save**
   - If you see a **Visibility** option on this screen, leave it on **Public**. "Private" here would make every staff member sign in to GitHub just to see the page.
5. **Wait a minute or two**, then refresh the Pages settings screen. Your address shows at the top, like:
   `https://yourgp.github.io/start/`
6. **Open it and check.** Click through Doctors, Reception/Admin and Coaches, and try a few links.

## Optional: a nicer address

You can use something like `start.ygp.au` instead of the github.io address.

1. In **Settings** > **Pages** > **Custom domain**, type `start.ygp.au` and save.
2. Ask whoever manages the ygp.au domain to add a DNS record:
   - Type: `CNAME`
   - Name: `start`
   - Value: `yourgp.github.io` (your GitHub account or organisation name + `.github.io`)
3. Once it's working (can take up to a day), tick **Enforce HTTPS**.

## Set it as the home page

- **One computer:** in Chrome or Edge, go to **Settings** > **On start-up** > **Open a specific page** and paste the address. Do the same under **Appearance** > **Show home button** if you want the home button too.
- **All clinic computers:** ask IT to push the home page through Intune or Group Policy, so every PC opens to it automatically.
- **Open on a specific view:** add the role to the end of the address.
  - Doctors: `.../start/` (the default)
  - Reception: `.../start/#reception`
  - Coaches: `.../start/#coaches`

  That means front desk PCs can open straight to reception links.

## Updating the page

Ask Claude for the change, for example "add HealthPathways to the doctors' links" or "post an urgent announcement for reception: phones down until 4pm". Claude gives you an updated `index.html`. Then:

1. Open the repo on GitHub.
2. Click **Add file** > **Upload files**, drag in the new `index.html`, and click **Commit changes**.
3. The live page updates in about a minute. Refresh to see it (Ctrl+Shift+R forces a fresh copy).

For tiny edits you can also click `index.html` on GitHub, click the pencil icon, change the text, and commit.

**Where things live in `index.html`:**

- `ANNOUNCEMENTS = [ ... ]`: announcements. An empty list `[]` hides the section.
- `ROLES = [ ... ]`: the menu, groups and links for each role.
- `YGP_APPS_URL`: where the YGP Apps menu item goes.

If an update breaks something, go to the repo's **Commits** list, open the last good version, and restore that file. GitHub keeps every version.

## Good to know

- **The code is private, the page is public.** Only your GitHub team can see or change the code. Anyone with the address can open the page itself, which is what we want since there's no login. The tools still need their own logins. Just don't put anything private in the announcements.
- **Search stays on the computer.** Typing in the doctors' search box never leaves the browser. The topic buttons send the search words to Google, so search conditions and drugs, never patient names.
- **Logos** come from each site's own icon and need the internet to show. If one fails, a simple line icon shows instead.
- **No server, no database, no running costs.** GitHub Pages hosts it for free.
