# Nageswara Rao Narakulla — Performance Marketing Portfolio

Static single-page portfolio. No build step, no dependencies, no framework.
Open `index.html` in a browser to preview it locally.

## Files

```
index.html                      the whole page (markup + CSS + 3 inline SVG diagrams)
images/
  nageswara-rao-narakulla.jpg   hero portrait (1000×1250, 4:5)
  process-diagram.png           About — plan/build/track/read/optimise
  cognitec-ga4-channels.jpg     Cognitec — GA4 traffic acquisition by channel
  cognitec-google-ads.jpg       Cognitec — Google Ads account overview
  ambulance-lp-desktop.jpg      24x7 Ambulance — landing page, desktop
  ambulance-lp-mobile.jpg       24x7 Ambulance — landing page, mobile
  gtm-tags.jpg                  Tracking — GTM container tags
  ga4-home.jpg                  Tracking — GA4 Home report
  google-ads-conversions.jpg    Tracking — Ads conversion actions by goal
.nojekyll                       tells GitHub Pages to serve the folder as-is
```

The media plan, keyword mapping, RSA copy, ICP framework and placement
diagrams are **inline SVG inside `index.html`** — not image files. Edit their
text directly in the markup; they use the page's CSS variables, so they follow
the palette automatically.

## Publishing on GitHub Pages

1. Create a repo (e.g. `shalini-portfolio`) and push these files to the **root**
   of the default branch — `index.html` must be at the top level, not inside a
   subfolder.
2. Repo → **Settings → Pages**.
3. Source: **Deploy from a branch**. Branch: `main`, folder: `/ (root)`. Save.
4. Live in a minute or two at `https://<username>.github.io/<repo>/`.

Custom domain: add it under Settings → Pages, then create a `CNAME` file in the
repo root containing just the domain.

## Before it goes public

### Required — the page does not work without these

| Placeholder | Where | What to put |
|---|---|---|
| `[[WHATSAPP_NUMBER]]` | hero chip, floating button | Number with country code, no `+` or spaces, e.g. `919876543210` |
| `[[RESUME_DRIVE_LINK]]` | nav Résumé button | Public Drive or PDF link |
| `GTM-XXXXXXX` | `<head>` and `<noscript>` | Nageswara's own GTM container ID, or delete both blocks |

**The WhatsApp number is the only contact route on the page right now.** The
contact section was removed, so there is no email, phone or LinkedIn anywhere.
Worth reconsidering before publishing — recruiters who want to forward a résumé
or check LinkedIn currently cannot.

### Should be filled

| Placeholder | Where |
|---|---|
| `[[SEARCH_CERT_URL]]`, `[[DISPLAY_CERT_URL]]`, `[[GA4_CERT_URL]]` | Certifications — Skillshop verify links |
| `[[ISSUER]]`, `[[CERTIFICATION NAME]]`, `[[CERT_URL]]`, `[[one line on what it covers]]` | Certifications — fourth card, or delete the card |
| `[[MONTH YYYY – MONTH YYYY]]` | Cognitec case study — engagement period |
| `[[tCPA / Max Conv.]]` | Media plan table — Cognitec bid strategy |
| `[[__ calls in first __ days · cost per call ₹__]]` | Ambulance case study — delete the row if there is no data yet |

Search for `[[` to find all of them. Twelve remain.

### Also worth checking

- **Amber `confirm` chips** appear on two spec rows (ambulance Period, Cognitec
  Role). They are visible on the page — resolve the facts, then remove the
  `<span class="chk">…</span>` tags.
- **Cognitec spend (₹213k) and daily budgets (₹2,000 / ₹6,000) are published.**
  No client instruction against it, but confirm Cognitec is comfortable. To
  hide: blur the Cost tile in `cognitec-google-ads.jpg` and drop the ₹ figures
  from the Result row.
- **Ad group names, keywords and RSA copy in the SVG diagrams are inferred**,
  not exported from the account. Verify against the real build.
- **Six empty creative placeholders** remain in the Meta section. Either add
  real creative images or delete the `.creatives` grid.
- **`100+ ICP frameworks built`** in the hero counters sits beside three `10+`
  figures. Consider whether it should be a smaller number, or relabelled to
  creatives / audience research exercises.
- **Image placeholders** still render as dashed boxes. Search for
  `class="ph ` — each one names the image it wants and the size.

## Editing notes

- Palette and fonts are CSS variables at the top of `index.html`
  (`--maroon`, `--brass`, `--teal`, `--ink`, `--paper`). Change once,
  applies everywhere including the SVG diagrams.
- Fonts load from Google Fonts. Offline the page falls back to system serif
  and mono — layout holds, character changes.
- WhatsApp clicks push a `whatsapp_click` dataLayer event with a
  `cta_location` parameter (`hero`, `floating`), so they are measurable once
  the GTM container is live.
- Responsive down to 360px. Wide elements (media plan table, SVG diagrams)
  scroll horizontally rather than shrinking their text.

## Note on the sibling portfolios

Same template as the Shalini Konda and Vikas Nair builds — same layout, palette
and case studies, with the name and portrait swapped. The three students are
from different batches.

If any two of them apply to the same employer, change the **Role** row on each
case study so it says what that person actually owned, and shift one page's
palette: the colours are five CSS variables at the top of `index.html`
(`--maroon`, `--brass`, `--teal`, `--paper`, `--ink`), and the inline SVG
diagrams follow them automatically.
