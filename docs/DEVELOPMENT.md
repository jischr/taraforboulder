# Tara for Boulder — development & deploy

Made with [Doks Starter theme](https://github.com/h-enk/doks)

Content updates (endorsers, quotes, issues) are done via the GitHub UI; see [README.md](README.md).

## Requirements

- [Git](https://git-scm.com/) — latest source release
- [Node.js](https://nodejs.org/) — v18 or newer (LTS recommended)

## Get started

### 1. Install dependencies

```bash
npm install
```

### 2. Start development server

```bash
npm run start
```

Open the URL shown (default http://localhost:1313).

### 3. Build for production

```bash
npm run build
```

Output is in the `public/` directory.

## Endorsements (2023 / 2026)

The live endorsers and quotes are in `data/endorsers-2023.yaml` and `data/quotes-2023.yaml`. To work on 2026 content without changing the live site, edit **data/endorsers-2026.yaml** and **data/quotes-2026.yaml**.

**To make 2026 the live version:** In `config/_default/params.toml` set `endorsementsYear = "2026"`, then build and deploy. The same URLs will show the 2026 content. Set back to `"2023"` to revert.

## Build & deploy

Netlify runs `npm run build` (with devDependencies installed). Hugo version is set in `package.json` under `otherDependencies.hugo` (currently 0.101.0).

## For repo owners: branches and release

- **dev** is the working branch. Content editors commit directly to **dev** (see [README.md](README.md)). If you don't have a `dev` branch yet, create it from `main` (e.g. in GitHub: switch to main, then create a new branch named `dev` from it).
- **main** is protected; no one should push or merge directly to main. To protect main: GitHub → Settings → Branches → Add rule → branch name pattern `main` → enable "Do not allow bypassing the above settings" and restrict who can push (e.g. no one, or only you).
- **Release:** When you're ready to update the live site, merge **dev** into **main**. Netlify will build and deploy from main. Optionally set **dev** as the default branch (Settings → General → Default branch) so editors start on dev when they open the repo.

## Documentation

- [Netlify](https://docs.netlify.com/)
- [Hugo](https://gohugo.io/documentation/)
- [Doks](https://getdoks.org/)
