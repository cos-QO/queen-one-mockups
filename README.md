# queen-one-mockups

Interactive wireframe prototypes for QueenOne / ConnectUI features.

Each wireframe is a **self-contained HTML file** — no build step, no dependencies to install. Open the preview link and the prototype runs in the browser.

---

## Wireframes

| Screen | Preview | Source |
|---|---|---|
| Assets Management | [Open preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/cos-QO/queen-one-mockups/main/wireframes/assets-management.html) | `wireframes/assets-management.html` |
| Asset Library — Table View | [Open preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/cos-QO/queen-one-mockups/main/wireframes/asset-library-table.html) | `wireframes/asset-library-table.html` |

---

## How to View

Click any **Open preview** link above. It opens via [htmlpreview.github.io](https://htmlpreview.github.io), which renders the raw HTML directly — no download needed.

You can also open the raw file URL directly:
```
https://raw.githubusercontent.com/cos-QO/queen-one-mockups/main/wireframes/<slug>.html
```

---

## Design System

All wireframes follow the same intentionally neutral rules:

- **Stack**: React 18 + MUI 5, loaded from CDN — no build step
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
/wireframe-publish <slug>                   # pushes the built HTML to this repo
```

The publish step base64-encodes the local file and pushes it to `wireframes/<slug>.html` on `main` via the GitHub MCP tool. The preview link is live as soon as the push succeeds.

To update an existing wireframe, rebuild the HTML locally and run `/wireframe-publish <slug>` again — it detects the existing file SHA and does an update commit.

---

## Repo Structure

```
wireframes/
  <slug>.html    # one file per screen or feature area
README.md
```

Wireframes are never deleted from this repo — they serve as a historical record of design decisions. Superseded versions are overwritten in place (same slug, new commit).
