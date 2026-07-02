# Omar Soubhi — Personal Landing Page

Single-file static site. No build step, no dependencies.

## Deploy to GitHub Pages

**Option A — user site (recommended):** repo named `<your-username>.github.io` → site lives at `https://<your-username>.github.io`

**Option B — project repo:** any repo name → site lives at `https://<your-username>.github.io/<repo-name>`

Steps (either option):

1. Create the repo on GitHub.
2. Upload `index.html` and this `README.md` (drag-and-drop on github.com works, or use git).
3. Repo → **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save.
4. Wait ~1 minute. Your site is live.

## Adding projects

Open `index.html` and find the `projects` array in the `<script>` block near the bottom. Each project is one object:

```js
{
  title: "My Tool Name",
  tag: "DATA",                    // short badge: PLANNING, DATA, AUTOMATION, etc.
  description: "One or two sentences on the problem it solved.",
  tech: ["Python", "SQL"],        // shows as pill tags
  link: "https://..."             // or null to hide the link icon
}
```

Add, remove, or reorder objects — the grid and the "Tools built" stat update automatically.

## Editing everything else

All content is plain HTML in `index.html`. Colors live in the `:root` CSS variables at the top of the `<style>` block — change `--accent` to re-theme the whole page.
