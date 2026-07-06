# Landing Page

Single-file static site. No build step, no dependencies, no name on the page.

## Files

- `index.html` — the landing page
- `schedule-auditor.html` — Schedule Auditor: upload a Primavera P6 `.xer` and get a DCMA 14-point assessment plus extra weakness checks (SF links, excessive lags, duplicate names, actual-date consistency), with per-check offender lists and CSV export. Parses the XER client-side; includes a sample schedule with seeded defects for demoing. Non-automatable checks (critical path test, exact CPLI) are marked "review" rather than guessed.
- `time-chainage.html` — Time-Chainage Creator: enter activities with chainages and dates (or durations) in a table or CSV, get a time-location diagram — sloped lines for linear works, vertical bands for fixed-location works, trade color-coding, SVG/PNG export. Sample 5 km road project included.
- `earned-value.html` — EV Engine: control accounts with BAC, dates, % complete, actual cost + a data date → CPI, SPI, CV/SV, EAC (three methods), VAC, TCPI, PV/EV/AC S-curves, and a per-activity performance table. Sample project included.
- `construction-dashboard.html` — Field Dashboard, a standalone tool linked from the Projects section. Ingests any construction CSV/XLSX export (auto-detects and lets you remap columns), then renders KPIs, a cost S-curve, budget vs actual by phase, completion by trade, a phase timeline, and a task register. 100% client-side; includes a "Load sample project" mode for demoing without data. Upload both files to the same repo — the project link is relative.

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
