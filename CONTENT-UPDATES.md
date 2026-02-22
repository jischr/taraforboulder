# Updating site content (endorsers, quotes, issues)

This guide is for anyone who updates content on the Tara for Boulder site using **only the GitHub website**—no coding experience or development environment needed.

---

## What you need

- A **GitHub account**
- **Permission to edit** this repo. Easiest: ask the repo owner to add you as a **collaborator** so you can edit and save directly. If you don’t have that, you can send your changes to someone who can commit them, or use the branch and pull request flow below.

---

## How to edit a file on GitHub (direct save)

1. Open this repo on GitHub and go to the file you want to edit (see the **What to edit** table below).
2. Click the **pencil icon** (“Edit this file”) at the top right of the file.
3. Make your changes in the text box.
4. Scroll down and click **Commit changes**. Leave **“Commit directly to the main branch”** selected.
5. Add a short commit message (e.g. “Update endorsers” or “Fix housing page”) and click **Commit changes** again.
6. The live site will update after the next deploy (usually a few minutes).

**Don’t see the pencil icon?** You don’t have edit access. Ask the repo owner to add you as a collaborator, or send your changes to someone who can commit them.

---

## Alternative: Using a branch and pull request

If your team prefers that changes go through a pull request (review before they go live), follow these steps.

### 1. Create a branch when you edit

1. Open the file and click the **pencil icon** to edit.
2. Make your changes.
3. **Before** clicking “Commit changes,” find the dropdown that says **“Commit directly to the main branch.”**
4. Change it to **“Create a new branch for this commit and start a pull request.”**
5. GitHub will suggest a branch name (e.g. `patch-1` or `update-endorsers`). You can use it or type a short name (e.g. `add-jane-doe-endorsement`).
6. Click **Commit changes.**

You only create one branch for this set of edits. You don’t need to “keep the branch up to date”—just make your edit, create the branch, and open the pull request.

### 2. Create the pull request

1. After you commit, GitHub will show **“Compare & pull request”** (a green button). Click it.  
   If you don’t see it, go back to the repo homepage; a yellow bar may appear saying your branch had recent pushes—click **Open pull request** there.
2. Add a short title (e.g. “Update endorsers”) and, if you like, a sentence describing the change.
3. Click **Create pull request.**
4. Someone with merge access will review and merge. Once merged, the site will update after the next deploy.

### 3. Delete the branch after merge (optional)

After the pull request is merged, GitHub will show a **“Delete branch”** (purple button) on the same page. Click it to remove the branch and keep the repo tidy. You don’t have to—leaving the branch doesn’t cause problems. The next time you want to update content, you’ll start from the main branch again and can either commit directly or create a new branch + pull request.

---

## What to edit (file map)

| What you want to change | File to open on GitHub |
|------------------------|------------------------|
| **Live endorsers list** (what’s on the site now) | [data/endorsers-2023.yaml](data/endorsers-2023.yaml) |
| **Live quotes from supporters** | [data/quotes-2023.yaml](data/quotes-2023.yaml) |
| **Draft 2026 endorsers** (not live yet) | [data/endorsers-2026.yaml](data/endorsers-2026.yaml) |
| **Draft 2026 quotes** | [data/quotes-2026.yaml](data/quotes-2026.yaml) |
| **Issue pages** (e.g. transportation, housing, safety) | [content/en/issues/content/](content/en/issues/content/) — then open the file you need (e.g. `transportation.md`, `housing.md`, `safecommunity.md`, `homelessness.md`, `climate.md`, `economicvitality.md`, `artsculture.md`, `growth.md`) |
| **Bio** | [content/en/bio/index.md](content/en/bio/index.md) |
| **Experience** | [content/en/experience/index.md](content/en/experience/index.md) |

---

## Rules when editing

### Endorsers and quotes (YAML files in `data/`)

- Use **2 spaces** for indentation. Don’t use tabs.
- To **add** an entry, copy an existing one and change the name, title, or quote.
- **Don’t remove or rename** the section headers (e.g. `organizations:`, `elected_officials:`, `community:`).

**Endorsers:** Each person or group belongs under one section. For **organizations**, each line is one name. For **elected officials**, **former officials**, and **board/commission**, each entry has `first_name:`, `last_name:`, and `title:` (no quotes needed). For **community**, each entry has `first_name:` and `last_name:` (the list is sorted by last name). Copy an existing entry and change the values; use 2 spaces for indentation.

**Quotes:** Each quote has `name:`, `title:` (optional), and `quote:` (the quote text). Copy an existing quote block and change the text.

### Issue pages, Bio, and Experience (markdown files)

- **Edit only the content below the line that says `<!-- EDIT BELOW -->`.**
- Don’t change or delete anything **above** that line (the “front matter” at the top). If you need to change the page title or short description, ask someone with experience or leave it as is.

---

## Making 2026 endorsements live (when ready)

The site currently shows 2023 endorsers and quotes. The 2026 lists live in `data/endorsers-2026.yaml` and `data/quotes-2026.yaml` and are hidden until one setting is changed.

1. Open [config/_default/params.toml](config/_default/params.toml) on GitHub and click the pencil icon to edit.
2. Find the line: `endorsementsYear = "2023"`.
3. Change it to: `endorsementsYear = "2026"`.
4. Commit the change (directly to main or via a branch + pull request, same as above).

After the next deploy, the site will show the 2026 endorsers and quotes. If you’re unsure about doing this, ask someone with access to make the change.

---

## After you save

If the repo is connected to Netlify (as this one is), pushing or merging to the main branch triggers a new build. The live site usually updates within a few minutes. If you used a branch and pull request, someone with merge access needs to merge the PR for the site to update.
