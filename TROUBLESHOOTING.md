# Troubleshooting Guide

## GitHub Pages Build Failures

### How to Check Build Status

1. Go to your repository on GitHub
2. Click the **Actions** tab
3. Look for the latest workflow run
4. If it failed, click on it to see the error details

### Common Issues and Fixes

#### ✅ Issue 1: "The theme minima could not be found"

**Solution:** Already fixed! We removed the theme declaration since we're using custom layouts.

#### ✅ Issue 2: Dependency conflicts with Gemfile

**Solution:** Already fixed! Simplified Gemfile to use only `github-pages` gem.

#### Issue 3: "Liquid Exception: Liquid syntax error"

**Cause:** Syntax error in a template or markdown file.

**How to find it:**
- Check the error message for the file name
- Look for unmatched {% raw %}`{%`{% endraw %} or {% raw %}`{{`{% endraw %} brackets
- Check for missing `endfor` or `endif` tags

**Solution:**
```bash
# Test locally first
bundle exec jekyll build
```

#### Issue 4: "GitHub Pages is not configured"

**Solution:**
1. Go to repository **Settings**
2. Click **Pages** in left sidebar
3. Under "Build and deployment":
   - Source: Select **GitHub Actions**
4. Save changes

#### Issue 5: "404 - Page not found" after successful build

**Cause:** Incorrect `baseurl` in `_config.yml`

**Solution:**
- For user site (`username.github.io`): `baseurl: ""`
- For project site (`username.github.io/repo-name`): `baseurl: "/repo-name"`

Check your `_config.yml`:
```yaml
url: "https://jrfaeder.io"
baseurl: "/faeder-lab"  # Must match your repo name exactly
```

#### Issue 6: Images not loading

**Cause:** Missing image files or incorrect paths

**Solution:**
1. Make sure images are committed to the repo
2. Check paths start with `/assets/images/`
3. Verify image files exist in the correct location
4. File names are case-sensitive!

#### Issue 7: "YAML Front Matter" errors

**Cause:** Invalid YAML syntax in front matter

**Check for:**
- Missing closing `---`
- Incorrect indentation
- Unquoted special characters
- Smart quotes instead of straight quotes

**Example - Bad:**
```yaml
---
title: Dr. Faeder's Lab  # Apostrophe breaks it!
---
```

**Example - Good:**
```yaml
---
title: "Dr. Faeder's Lab"  # Quoted is safe
---
```

### Testing Locally Before Pushing

To catch errors before pushing to GitHub:

```bash
# Install dependencies (first time only)
bundle install

# Build the site
bundle exec jekyll build

# Or run a local server
bundle exec jekyll serve

# Visit http://localhost:4000
```

If it builds locally, it should build on GitHub Pages!

### Viewing Build Logs

1. Go to **Actions** tab
2. Click on the failed workflow
3. Click on the **build** job
4. Expand each step to see details
5. Look for error messages in red

### Getting More Help

#### Check These First:
- [ ] Is GitHub Pages enabled? (Settings → Pages)
- [ ] Is the workflow file present? (`.github/workflows/jekyll-gh-pages.yml`)
- [ ] Are all files committed and pushed?
- [ ] Does the site build locally?

#### Specific Error Messages:

**"Could not find gem"**
- Gemfile issue
- Try: `bundle update`

**"Liquid Exception"**
- Template syntax error
- Check the file mentioned in error
- Look for unmatched brackets

**"YAML Exception"**
- Front matter syntax error
- Check for proper indentation
- Quote strings with special characters

**"File to import not found"**
- Missing SCSS file
- Check `assets/css/style.scss` exists

### Quick Fixes Checklist

If build is failing, try these in order:

1. **Check workflow file exists:**
   ```
   .github/workflows/jekyll-gh-pages.yml
   ```

2. **Verify _config.yml:**
   - No `theme:` line (we use custom layouts)
   - Correct `baseurl`
   - Proper YAML syntax

3. **Test Gemfile:**
   ```bash
   bundle install
   bundle exec jekyll build
   ```

4. **Check all markdown files:**
   - Valid front matter (between `---`)
   - No liquid syntax errors
   - Proper indentation

5. **Verify image paths:**
   - Start with `/assets/images/`
   - Files actually exist
   - Correct case

6. **Push and wait:**
   ```bash
   git add .
   git commit -m "Fix build issues"
   git push
   ```
   - Wait 2-3 minutes
   - Check Actions tab

### Still Not Working?

1. **Copy the exact error message** from the Actions tab
2. **Check which file** is mentioned in the error
3. **Look at that file** for syntax errors
4. **Google the error message** - someone else has probably solved it!

### Common Error Messages Decoded

| Error | What It Means | Fix |
|-------|---------------|-----|
| "Liquid syntax error" | Template code is broken | Check {% raw %}`{%`{% endraw %} and {% raw %}`{{`{% endraw %} brackets match |
| "YAML exception" | Front matter is invalid | Check indentation and quotes |
| "Could not find gem" | Missing dependency | Check Gemfile |
| "404 not found" | Wrong baseurl | Update `_config.yml` |
| "No GitHub Pages site" | Pages not enabled | Enable in Settings |

### Emergency Reset

If nothing works, try this:

1. **Delete the workflow file:**
   ```bash
   rm .github/workflows/jekyll-gh-pages.yml
   ```

2. **Use GitHub's default Jekyll:**
   - Settings → Pages
   - Source: **Deploy from a branch**
   - Branch: **main** / **(root)**

This uses GitHub's built-in Jekyll, which is simpler but less customizable.

### Contact

If you've tried everything:
1. Check [Jekyll troubleshooting](https://jekyllrb.com/docs/troubleshooting/)
2. Check [GitHub Pages docs](https://docs.github.com/en/pages)
3. Open an issue in the repository with:
   - The error message
   - What you've tried
   - Your `_config.yml` contents

---

**Most Common Fix:** Make sure GitHub Pages is set to use **GitHub Actions** as the source (not "Deploy from a branch")!
