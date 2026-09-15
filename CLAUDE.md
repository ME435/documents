# documents (ME435 / CSSE435)

Course documents for ME435/CSSE435 (Rose-Hulman, Dr. Fisher). Right now the repo holds two student-facing setup guides, converted from the original Google Docs into Markdown so they can be edited and version-controlled here instead of in Docs.

## What's in `InstallationGuides/`

- **`Computer_Installation_Guide.md`** — setup on the student's own laptop: command line basics (incl. Windows quirks), Git, VS Code + extensions, Python/pip, MQTT, PySerial, and cloning the student's Github Classroom repo.
- **`Pi_Installation_Guide.md`** — setup performed on **each of the student's three Raspberry Pis**: a Pi 400, a Raspberry Pi 4B mounted on a Freenove car (the class's rover platform), and a Pi 5. Covers imaging the SD card, password/hostname/SSH/serial/I2C config, networking + Rose-Hulman EIT registration, and Python/MQTT/gpiozero installs.
- **`images/computer/`** and **`images/pi/`** — screenshots referenced by the two guides.

These two guides are meant to stay in sync with each other (they cross-link) and are actively being revised with Dr. Fisher — expect ongoing small wording/image edits rather than one-time authorship.

## Conventions to follow when editing these guides

**Images.** Every image is embedded as an HTML `<img>` tag, not `![]()` markdown — this lets each image get an explicit `width` or `height` so it renders at a sane size instead of full resolution. Rough sizing convention already in use:
- Small toolbar icons (e.g. `terminal-icon.png`, `networking-icon.png`): `width="180"`
- Dialog/menu screenshots that need to stay legible: `width="400"`–`"600"`
- Wide composite screenshots (menu + dialog side by side): `width="600"`
- Product/kit photos in the top table: `height="180"` (so the three table images line up at the same height regardless of their native aspect ratio)

Keep new images in `InstallationGuides/images/<computer|pi>/` and give them descriptive filenames (not `imageN.png`).

**Terminology.** The rover platform is a **Freenove car** with a Raspberry Pi 4B — never "tank" / "RaspTank" (that was the old hardware; it's been fully renamed throughout both docs). The three devices are consistently: **Pi 400**, **car** (or "car's Pi"), **Pi 5**. Hostnames follow `username-pi400`, `username-car`, `username-pi5`.

**Links.** Prefer `raspberrypi.com` over `raspberrypi.org` (the `.org` domain 302-redirects to `.com`, but some deep doc paths 404 after the redirect — verify a replacement URL actually loads before swapping it in, don't just do a blind domain substitution). Several links from the original Google Docs pointed at private Rose-Hulman resources (a Mac-address-collection spreadsheet, a Github Classroom setup doc, a couple of internal troubleshooting docs, links to other course-day docs) that don't resolve from the PDF export — these are marked `*(TODO: add link)*` in place rather than guessed at. Run `grep -rn TODO InstallationGuides/*.md` to find the current list before assuming the guides are link-complete.

**Headings / TOC.** Both guides have a hand-written Table of Contents near the top that links to `#heading-slug` anchors. If you rename a heading, update its TOC entry to match GitHub's slug rules (lowercase, spaces → hyphens, punctuation other than hyphens stripped) or the link breaks.

## Workspace setup

`.vscode/settings.json` + `.vscode/markdown-light.css` force VS Code's built-in Markdown preview to a light/GitHub-like look regardless of the editor's color theme (David prefers previewing with a white background since that matches how these render on github.com). This is repo-local and doesn't touch global VS Code settings.
