# itdepends.be

Personal website for Jan De Dobbeleer - Engineering Leader & Open Source Innovator.

## GitHub Pages Deployment

This site is configured to deploy to GitHub Pages using GitHub Actions.

### Setup Instructions

1. **Set the main branch as default**: After merging this PR, go to repository settings and set `main` as the default branch.

2. **Enable GitHub Pages**: 
   - Go to repository Settings → Pages
   - Under "Source", select "GitHub Actions"
   - The site will automatically deploy when changes are pushed to the `main` branch

3. **Configure Custom Domain** (if desired):
   - In Settings → Pages, add `itdepends.be` as the custom domain
   - Update DNS records to point to GitHub Pages

### Deployment

The site automatically deploys on every push to the `main` branch using the workflow defined in `.github/workflows/deploy.yml`.

You can also manually trigger a deployment from the Actions tab.

## Local Development

This is a static HTML site. Simply open `index.html` in a web browser to view locally.

## Structure

- `index.html` - Main landing page
- `rates.html` - Rates information page
- `img/` - Images and icons
- `_headers` - Netlify headers configuration (not used by GitHub Pages)
