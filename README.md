# Tara for Boulder

Made with [Doks Starter theme](https://github.com/h-enk/doks)

**Updating site content (endorsers, quotes, issues)?** See [CONTENT-UPDATES.md](CONTENT-UPDATES.md) for step-by-step instructions using GitHub in your browser—no dev environment needed.

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

See [CONTENT-UPDATES.md](CONTENT-UPDATES.md) for how to edit these files (and issue pages, bio, experience) via the GitHub UI.

## Build & deploy

Netlify runs `npm run build` (with devDependencies installed). Hugo version is set in `package.json` under `otherDependencies.hugo` (currently 0.101.0).

## Documentation

- [Netlify](https://docs.netlify.com/)
- [Hugo](https://gohugo.io/documentation/)
- [Doks](https://getdoks.org/)
