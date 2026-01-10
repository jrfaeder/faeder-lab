# Contributing to the Faeder Lab Website

Thank you for contributing to our lab website! This guide will help you make updates safely and effectively.

## Quick Reference

### I want to...

- **Update my bio or contact info** → Edit `_data/team.yml`
- **Add a news item or update** → Edit `index.md`
- **Update research descriptions** → Edit `research.md`
- **Add publications** → Edit `publications.md` or update your ORCID profile
- **Change a page's content** → Edit the corresponding `.md` file
- **Add a new page** → Create a new `.md` file and add it to `_config.yml` navigation

## For Beginners: Editing Through GitHub

You don't need to install anything! Edit directly on GitHub:

1. **Find the file** you want to edit in the repository
2. **Click the pencil icon** (✏️) in the top right
3. **Make your changes** using [Markdown syntax](https://www.markdownguide.org/basic-syntax/)
4. **Preview** your changes by clicking the "Preview" tab
5. **Describe your changes** in the box at the bottom
6. **Click "Commit changes"**

Your changes will go live automatically within a few minutes!

## Markdown Basics

```markdown
# Heading 1
## Heading 2
### Heading 3

**bold text**
*italic text*

[Link text](https://url.com)

- Bullet point
- Another bullet point

1. Numbered list
2. Another item

![Image alt text](/path/to/image.jpg)
```

## Adding Team Members

1. Open `_data/team.yml`
2. Add a new entry following this format:

```yaml
- name: "Your Name"
  role: "PhD Student"  # or Postdoctoral Researcher, etc.
  image: "/assets/images/team/yourname.jpg"
  bio: "Brief description of your research interests."
  email: "youremail@pitt.edu"
  github: "yourusername"  # optional
  twitter: "yourhandle"   # optional
  orcid: "https://orcid.org/0000-0000-0000-0000"  # optional
  order: 10  # lower numbers appear first
```

3. Upload your photo:
   - Go to `assets/images/team/`
   - Click "Add file" → "Upload files"
   - Drag your photo (recommended: 300x300px, JPG or PNG)
   - Name it `yourname.jpg`

## Adding Publications

### Option 1: Keep ORCID Updated (Recommended)
Simply keep your ORCID profile current. The publications page links to ORCID for the complete list.

### Option 2: Add to publications.md
Edit `publications.md` and add your publication in the appropriate section:

```markdown
- **Title of Your Paper**
  Journal Name, Year
  Brief description or link
```

## Adding Images

1. Upload to `assets/images/` (or a subfolder like `assets/images/research/`)
2. Reference in markdown:
   ```markdown
   ![Description](/assets/images/filename.jpg)
   ```

## Testing Changes Locally (Advanced)

If you want to preview changes before pushing:

```bash
# Install dependencies (first time only)
bundle install

# Run local server
bundle exec jekyll serve

# Open http://localhost:4000 in your browser
```

## Common Issues

### Changes aren't showing up
- Wait 2-3 minutes for GitHub Pages to rebuild
- Check the "Actions" tab for build status
- Hard refresh your browser (Cmd+Shift+R or Ctrl+Shift+R)

### Broken formatting
- Check your Markdown syntax
- Make sure YAML front matter (the stuff between `---`) is valid
- Look for missing quotes around special characters

### Image not showing
- Verify the path starts with `/assets/images/`
- Check that you committed/uploaded the image file
- File names are case-sensitive!

## Best Practices

1. **Write clear commit messages**
   - Good: "Add publication about rule-based modeling"
   - Bad: "update"

2. **Preview before committing**
   - Use GitHub's preview tab
   - Or test locally if making major changes

3. **Keep it simple**
   - Use markdown for formatting, not HTML
   - Don't modify CSS unless you know what you're doing

4. **Update regularly**
   - Keep your profile current
   - Add new publications promptly
   - Update research interests as they evolve

## Need Help?

- Check the [README.md](README.md) for more detailed documentation
- Ask a lab member who's contributed before
- Open an issue on GitHub if something's broken
- Email the lab web administrator

## Style Guidelines

### Writing
- Use clear, concise language
- Write in third person for official pages
- First person is fine for personal bios
- Avoid jargon where possible

### Images
- Photos: 300x300px for team members, larger for research images
- Format: JPG for photos, PNG for diagrams
- Keep file sizes reasonable (< 500KB when possible)

### Tone
- Professional but approachable
- Emphasize scientific rigor and collaboration
- Be inclusive and welcoming

Thank you for helping maintain our lab's web presence!
