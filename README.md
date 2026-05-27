# ZH Creative LLC

A static React site deployed to GitHub Pages with a custom domain.

## Prerequisites (MacOS)

### Xcode Command Line Tools

```bash
xcode-select --install
```

### Node.js

```bash
brew install node
```

Verify installation:

```bash
node -v
npm -v
```

### Git

```bash
brew install git
```

Verify installation:

```bash
git --version
```

### GitHub CLI (optional)

```bash
brew install gh
gh auth login
```

## Getting Started

### Clone the repository

```bash
git clone https://github.com/KyleNewton10/ZachSite.git
cd ZachSite
```

### Install dependencies

```bash
npm install
```

### Start development server

```bash
npm run dev
```

The site will be available at `http://localhost:5173`.

## File Structure

| File | Purpose |
|------|---------|
| `src/App.jsx` | Main component — edit this to change content |
| `src/index.css` | Tailwind CSS directives |
| `src/App.css` | Global CSS styles |
| `src/main.jsx` | React entry point |
| `index.html` | HTML entry point |
| `vite.config.js` | Vite config — base path |
| `tailwind.config.js` | Tailwind CSS config |
| `postcss.config.js` | PostCSS config |
| `package.json` | Dependencies and scripts |

## Making Changes

1. Edit `src/App.jsx` to update content
2. Preview locally with `npm run dev`
3. Build to verify: `npm run build`

## Pushing Changes

```bash
git add .
git commit -m "description of changes"
git push
```

## Deploying

```bash
npm run deploy
```

This builds the site and pushes the `dist/` folder to the `gh-pages` branch. GitHub serves the site from that branch.

## Custom Domain (GoDaddy)

### Add CNAME record

1. Log in to [GoDaddy](https://godaddy.com)
2. Go to **DNS** for `tidepool.tech`
3. Add a CNAME record:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | test_inquery | kylenewton10.github.io | Default |

4. Save

### Configure GitHub Pages

1. Go to your repo → **Settings > Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `gh-pages`
4. **Folder**: `/ (root)`
5. **Custom domain**: `test_inquery.tidepool.tech`
6. Click **Save**
7. Check **Enforce HTTPS**

DNS propagation can take up to 48 hours.

## Troubleshooting

- **Blank page**: Check browser console for 404 errors on assets
- **MIME type error**: Verify GitHub Pages is serving from `gh-pages` branch
- **CNAME not working**: Wait for DNS propagation, verify record type is CNAME
