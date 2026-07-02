# Landing Page

Single-file static site. No build step, no dependencies, no name on the page.

## Deploy to GitHub Pages

**Option A — user site:** repo named `<your-username>.github.io` → site at `https://<your-username>.github.io`

**Option B — project repo:** any repo name → site at `https://<your-username>.github.io/<repo-name>`

Steps (either option):

1. Create the repo on GitHub.
2. Upload `index.html` and this `README.md`.
3. Repo → **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save.
4. Wait ~1 minute. Live.

Note: option A puts your GitHub username in the URL — if full anonymity matters, use a project repo or a custom domain.

## Adding projects

Open `index.html`, find the `projects` array in the `<script>` block near the bottom. One object per project:

```js
{
  title: "My Tool Name",
  category: "Data",              // mono label shown in the index row
  year: "2025",
  description: "One or two sentences on the problem it solved.",
  tech: ["Python", "SQL"],       // pill tags inside the expanded row
  link: "https://..."            // or null to hide the link
}
```

The index table, entry counter, and "tools in service" stat all update automatically.

## Theming

Colors are CSS variables in `:root` at the top of the `<style>` block. `--accent` (currently signal orange `#ff4d00`) drives the whole identity — change one line to re-theme.
