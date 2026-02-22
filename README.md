# Updating site content

This guide is for anyone who updates content on the Tara for Boulder site using **only the GitHub website**—no coding experience or development environment needed.

---

## What you need

- A **GitHub account**
- **Permission to edit** this repo (so you see the pencil icon when you open a file). You commit your changes **directly to the dev branch**. The repo owner handles merging dev into main when they're ready to update the live site.

---

## How to edit a file on GitHub

1. Find the file you want to edit in the **What to edit** table below.
2. Click on the link (helpful to open in a new tab).
3. Click the **pencil icon** to edit at the top of the file.
4. Make your changes in the text box.
5. Scroll down and click **Commit changes**. Leave **"Commit directly to the dev branch"** selected
6. Add a short commit message (e.g. "Update endorsers") and click **Commit directly to dev branch** again.

Your changes are now on **dev**. The live site will update when the repo owner merges dev into main for a release.

---

## What to edit (file map)

| What you want to change | File to open on GitHub |
|------------------------|------------------------|
| **Live endorsers list** (what's on the site now) | [data/endorsers-2023.yaml](data/endorsers-2023.yaml) |
| **Live quotes from supporters** | [data/quotes-2023.yaml](data/quotes-2023.yaml) |
| **Draft 2026 endorsers** (not live yet) | [data/endorsers-2026.yaml](data/endorsers-2026.yaml) |
| **Draft 2026 quotes** | [data/quotes-2026.yaml](data/quotes-2026.yaml) |
| **Issue pages** (e.g. transportation, housing, safety) | [content/en/issues/content/](content/en/issues/content/) — then open the file you need (e.g. `transportation.md`, `housing.md`, `safecommunity.md`, `homelessness.md`, `climate.md`, `economicvitality.md`, `artsculture.md`, `growth.md`) |
| **Bio** | [content/en/bio/index.md](content/en/bio/index.md) |
| **Experience** | [content/en/experience/index.md](content/en/experience/index.md) |

---

## Rules when editing

### Endorsers and quotes (YAML files in `data/`)

- To **add** an entry, copy an existing one and change the name, title, or quote.
- **Don't remove or rename** the section headers (e.g. `organizations:`, `elected_officials:`, `community:`).

**Endorsers:** Each person or group belongs under one section. For **organizations**, each line is one name. For **elected officials**, **former officials**, and **board/commission**, each entry has `first_name:`, `last_name:`, and `title:`. For **community**, each entry has `first_name:` and `last_name:` (the list is sorted by last name). Copy an existing entry and change the values; use 2 spaces for indentation.

**Quotes:** Each quote has `name:`, `title:` (optional), and `quote:` (the quote text). Copy an existing quote block and change the text.

### Issue pages, Bio, and Experience (markdown files)

- **Edit only the content below the line that says `<!-- EDIT BELOW -->`.**
- Don't change or delete anything **above** that line (the "front matter" at the top). If you need to change the page title or short description, ask someone with experience or leave it as is.

---

## Making 2026 endorsements live (when ready)

The site currently shows 2023 endorsers and quotes. The 2026 lists live in `data/endorsers-2026.yaml` and `data/quotes-2026.yaml` and are hidden until one setting is changed.

1. Open [config/_default/params.toml](config/_default/params.toml) on GitHub and click the pencil icon to edit.
2. Find the line: `endorsementsYear = "2023"`.
3. Change it to: `endorsementsYear = "2026"`.
4. Commit the change **to the dev branch** (same as above—commit directly to dev). The 2026 content will be on dev; the live site will show it after the repo owner merges dev into main for a release.

If you're unsure about doing this, ask someone with access.

---

## After you save

Your commit goes **to dev**. The **live site** (production) updates when the repo owner merges **dev** into **main** and deploys—so your content will appear on the live site at the next release, not immediately after you commit.

---

For setup, local development, build & deploy, and repo-owner release steps, see [DEVELOPMENT.md](DEVELOPMENT.md).
