# Setup Guide for the Faeder Lab Website

This guide will walk you through setting up your new lab website on GitHub Pages.

## Step 1: Update Configuration

1. Open `_config.yml`
2. Update these values:
   - `url`: Will be `https://YOUR-GITHUB-USERNAME.github.io`
   - `baseurl`:
     - If using a user/organization site (yourusername.github.io), leave empty: `baseurl: ""`
     - If using a project site, use the repo name: `baseurl: "/faeder-lab"`
   - `author.email`: Your email
   - `author.orcid`: Your ORCID URL (get one at https://orcid.org if you don't have it)
   - `social`: Add your social media handles (optional)

## Step 2: Add Your Profile Information

1. Open `_data/team.yml`
2. Update the Principal Investigator entry with your information
3. Update the ORCID URL

## Step 3: Add Your Photo

1. Prepare a professional photo:
   - Square format (300x300px recommended)
   - JPG or PNG format
   - Good lighting, professional appearance
   - File size under 500KB

2. Save it as `faeder.jpg` in `assets/images/team/`

3. If you want to use a different filename, update the `image` path in `_data/team.yml`

## Step 4: Create GitHub Repository

1. Go to https://github.com/new
2. Repository name:
   - For a user site: `YOUR-USERNAME.github.io`
   - For a project site: `faeder-lab` (or any name you prefer)
3. Make it **Public**
4. Do NOT initialize with README, .gitignore, or license (we already have these)
5. Click "Create repository"

## Step 5: Push Your Code to GitHub

Open Terminal and run these commands:

```bash
# Navigate to your website directory
cd "/Users/faeder/Library/CloudStorage/OneDrive-UniversityofPittsburgh/Code/Website"

# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Faeder Lab website"

# Rename branch to main
git branch -M main

# Add your GitHub repository (replace with YOUR repository URL)
git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git

# Push to GitHub
git push -u origin main
```

## Step 6: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right)
3. Click **Pages** in the left sidebar
4. Under "Build and deployment":
   - Source: Select "GitHub Actions"
5. The workflow is already set up, so it should deploy automatically!

## Step 7: Wait for Deployment

1. Go to the **Actions** tab in your repository
2. You should see a workflow running
3. Wait for it to complete (usually 1-2 minutes)
4. Once complete, your site will be live!

Your site URL will be:
- User site: `https://YOUR-USERNAME.github.io/`
- Project site: `https://YOUR-USERNAME.github.io/REPO-NAME/`

## Step 8: Verify Your Site

1. Visit your site URL
2. Check that everything looks correct
3. Test all navigation links
4. Verify your photo appears

## Step 9: Update Content

Now customize your content:

1. **Home page** (`index.md`): Update the welcome message and highlights
2. **Research** (`research.md`): Customize research areas and descriptions
3. **Publications** (`publications.md`): Add your publications or verify ORCID link
4. **Team** (`_data/team.yml`): Add other lab members

For each change:
```bash
# Make your edits, then:
git add .
git commit -m "Describe what you changed"
git push
```

The site will automatically rebuild and update within 2-3 minutes.

## Optional: Custom Domain

If you want to use a custom domain (e.g., faederlab.org):

1. Purchase a domain from a registrar (Namecheap, Google Domains, etc.)
2. In your repository Settings → Pages:
   - Enter your custom domain
   - Check "Enforce HTTPS" (after DNS propagates)
3. In your domain registrar's DNS settings, add:
   - For apex domain (faederlab.org):
     ```
     A record → 185.199.108.153
     A record → 185.199.109.153
     A record → 185.199.110.153
     A record → 185.199.111.153
     ```
   - For www subdomain:
     ```
     CNAME record → YOUR-USERNAME.github.io
     ```
4. Create a `CNAME` file in your repository root with your domain name
5. Wait for DNS to propagate (can take up to 48 hours)

See [GitHub's custom domain guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) for details.

## Testing Locally (Optional)

To preview changes before pushing:

1. Install Ruby (if not already installed):
   - Mac: Ruby is pre-installed, but you may want a newer version via Homebrew: `brew install ruby`
   - Windows: Use [RubyInstaller](https://rubyinstaller.org/)
   - Linux: `sudo apt-get install ruby-full` (Ubuntu/Debian)

2. Install Bundler:
   ```bash
   gem install bundler
   ```

3. Install dependencies:
   ```bash
   cd "/Users/faeder/Library/CloudStorage/OneDrive-UniversityofPittsburgh/Code/Website"
   bundle install
   ```

4. Run local server:
   ```bash
   bundle exec jekyll serve
   ```

5. Open http://localhost:4000 in your browser

6. The site will auto-reload when you save file changes

## Troubleshooting

### Build Failed
- Check the Actions tab for error messages
- Verify `_config.yml` syntax (YAML is picky about indentation)
- Make sure all front matter (between `---`) is valid

### Images Not Showing
- Check file paths are correct
- Verify images were committed and pushed
- File names are case-sensitive

### Changes Not Appearing
- Wait 2-3 minutes for rebuild
- Hard refresh browser (Cmd+Shift+R or Ctrl+Shift+R)
- Check Actions tab to ensure build succeeded

### Page Not Found (404)
- Verify `baseurl` in `_config.yml` matches your repository name
- Check that Pages is enabled in repository settings

## Next Steps

1. Share the website URL with your lab members
2. Have them add their profiles to `_data/team.yml`
3. Set up a regular schedule to update publications
4. Consider adding blog posts or news updates (optional)

## Getting Help

- **Jekyll docs**: https://jekyllrb.com/docs/
- **GitHub Pages docs**: https://docs.github.com/en/pages
- **Markdown guide**: https://www.markdownguide.org/
- **GitHub community**: https://github.community/

For lab-specific questions, refer to [README.md](README.md) and [CONTRIBUTING.md](CONTRIBUTING.md).

---

**Congratulations!** Your lab website is now set up. Welcome to the modern, markdown-based web! 🎉
