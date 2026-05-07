# queen-one-mockups

Interactive wireframe prototypes for QueenOne / ConnectUI features.

Each wireframe is a **self-contained HTML file** — no build step, no dependencies to install. Open the preview link and the prototype runs in the browser.

---

## Wireframes

| Screen | Preview | File |
|---|---|---|
| Creativesphere Assets | [Open preview](https://cos-qo.github.io/queen-one-mockups/wireframes/creativesphere-assets.html) | `wireframes/creativesphere-assets.html` |

---

## How to View

Each wireframe file in `wireframes/` can be previewed via GitHub Pages:

```
https://cos-qo.github.io/queen-one-mockups/wireframes/<slug>.html
```

---

## Design System

All wireframes follow the same intentionally neutral rules:

- **Stack**: React 18 + MUI 5, loaded from CDN — so no build step
- **Color palette**: grayscale only — no brand colors, no hex values outside the approved set
- **Elevation**: borders (`#E0E0E0`) only — no shadows, no MUI `elevation` props
- **Typography**: Inter (Google Fonts CDN)
- **Interactivity**: all screens, modals, drawers, and overlays are wired — nothing is static
- **Upgrade comments**: each major section is annotated with the ConnectUI/Orion component and token that would replace it in production

The neutral palette is intentional. Wireframes communicate **layout and flow**, not visual style. Brand colors and component variants are applied when the wireframe is implemented in ConnectUI.

---

## Adding a Wireframe

Wireframes are generated and published from the `cc-qo` Claude Code setup using two skills:

```
/wireframe <LIN-123 | description | url>   # scopes screens → creates brief + execution plan
/wireframe-publish <slug>                  # pushes the built HTML to this repo
```

The publish step base64-encodes the local file and pushes it to `wireframes/<slug>.html` on `main` via the GitHub MCP tool. The preview link is live as soon as the push succeeds.

To update an existing wireframe, rebuild the HTML locally and run `/wireframe-publish <slug>` again — it detects the existing file SHA and does an update commit.

---

## Repo Structure

```
wireframes/
  <slug>.html     # one file per screen or feature area
README.md
```