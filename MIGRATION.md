# GitHub Pages Migration Instructions

## Overview

This PR prepares the repository for GitHub Pages deployment by adding the necessary GitHub Actions workflow and documentation.

## What's Included

1. **GitHub Actions Workflow** (`.github/workflows/deploy.yml`)
   - Automatically deploys the site to GitHub Pages when changes are pushed to `main`
   - Can be manually triggered from the Actions tab
   - Uses official GitHub Actions for secure and reliable deployment

2. **Documentation** (`README.md`)
   - Setup instructions
   - Deployment information
   - Repository structure

## Steps to Complete Migration

### 1. Create the main branch

After reviewing and approving this PR, follow these steps to create the `main` branch:

**Option A: Merge this PR to main** (Recommended)
- When merging this PR, change the base branch from the default to `main` (create new branch if it doesn't exist)
- Or manually create and push the main branch from this feature branch

**Option B: Manual branch creation** (Alternative)
```bash
# Checkout the PR branch locally
git fetch origin copilot/migrate-to-github-pages
git checkout copilot/migrate-to-github-pages

# Create and push main branch
git checkout -b main
git push -u origin main
```

### 2. Set main as default branch

1. Go to repository Settings → General → Default branch
2. Change default branch from current default to `main`
3. Click "Update" and confirm

### 3. Enable GitHub Pages

1. Go to repository Settings → Pages
2. Under "Build and deployment":
   - Source: Select **"GitHub Actions"**
3. The site will automatically deploy on the next push to `main`

### 4. Configure Custom Domain (Optional)

If you want to use the custom domain `itdepends.be`:

1. In Settings → Pages → Custom domain, enter: `itdepends.be`
2. Update your DNS records to point to GitHub Pages:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
   Value: 185.199.109.153
   Value: 185.199.110.153
   Value: 185.199.111.153
   
   Type: CNAME
   Name: www
   Value: jandedobbeleer.github.io
   ```

### 5. Verify Deployment

1. Go to the Actions tab
2. Watch the "Deploy static content to Pages" workflow run
3. Once complete, visit your GitHub Pages URL to verify the site is live

## Notes

- The `_headers` file is specific to Netlify and won't be used by GitHub Pages
- GitHub Pages uses different header configuration methods if needed (through Jekyll or custom Actions)
- All static files (HTML, images, etc.) will be served as-is
