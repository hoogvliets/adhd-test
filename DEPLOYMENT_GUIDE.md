# GitHub Pages Deployment Guide

This guide will walk you through deploying your ADHD screening test to GitHub Pages.

## Prerequisites

- A GitHub account
- Git installed on your computer
- This project folder

## Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the **+** icon in the top right and select **New repository**
3. Choose a repository name (e.g., `adhd-screening-test`)
4. Set visibility to **Public** (required for free GitHub Pages)
5. **Do NOT** initialize with README, .gitignore, or license (we already have these files)
6. Click **Create repository**

## Step 2: Initialize Git and Push Your Code

Open Terminal and navigate to your project folder:

```bash
cd /Users/raphaelh/code/tinkering/adhd-test

# Initialize git repository
git init

# Add all files
git add .

# Create your first commit
git commit -m "Initial commit: ADHD screening test"

# Add your GitHub repository as remote (replace YOUR-USERNAME and REPO-NAME)
git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top navigation)
3. Click **Pages** (left sidebar)
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

## Step 4: Access Your Live Site

After a few minutes, your site will be live at:

```
https://YOUR-USERNAME.github.io/REPO-NAME/
```

GitHub will show you the URL in the Pages settings once deployment is complete.

## Step 5: Update README (Optional)

Update the placeholder URL in your README.md:

```markdown
🔗 **[Take the Test](https://YOUR-USERNAME.github.io/REPO-NAME/)**
```

Then commit and push:

```bash
git add README.md
git commit -m "Update live site URL"
git push
```

## Troubleshooting

### Site Not Loading

- Wait 2-5 minutes after enabling Pages
- Check that `index.html` is in the root directory
- Verify the repository is public
- Check the Actions tab for deployment status

### 404 Error

- Ensure the branch name is correct (`main` not `master`)
- Verify the folder is set to `/ (root)`
- Check that `.nojekyll` file exists

### Changes Not Appearing

- GitHub Pages can take 1-2 minutes to update
- Hard refresh your browser (Cmd+Shift+R on Mac)
- Clear browser cache

## Custom Domain (Optional)

To use a custom domain:

1. In repository Settings → Pages
2. Enter your custom domain
3. Add DNS records at your domain provider:
   - Type: `CNAME`
   - Name: `www` (or subdomain)
   - Value: `YOUR-USERNAME.github.io`

## Making Updates

To update your live site:

```bash
# Make your changes to index.html or other files
git add .
git commit -m "Description of changes"
git push
```

Changes will appear on your live site within 1-2 minutes.

## Need Help?

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Pages Troubleshooting](https://docs.github.com/en/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites)

---

**That's it!** Your ADHD screening test is now live and accessible to anyone with the URL.
