# Quick Start Guide

**Get your lab website live in 15 minutes!**

## Prerequisites
- A GitHub account
- Your professional photo ready (300x300px, JPG)
- Your ORCID ID (or sign up at https://orcid.org)

## Steps

### 1. Create GitHub Repository (2 min)
```
1. Go to https://github.com/new
2. Name: "YOUR-USERNAME.github.io" (user site) OR "faeder-lab" (project site)
3. Public repository
4. Don't initialize with README
5. Click "Create repository"
```

### 2. Configure Site (3 min)
Edit `_config.yml`:
```yaml
url: "https://YOUR-USERNAME.github.io"
baseurl: ""  # OR "/faeder-lab" for project site

author:
  email: "faeder@pitt.edu"
  orcid: "https://orcid.org/YOUR-ORCID-ID"

social:
  github: "YOUR-USERNAME"
```

### 3. Add Your Photo (2 min)
- Save your photo as `assets/images/team/faeder.jpg`
- Update path in `_data/team.yml` if using different name

### 4. Update Your Profile (3 min)
Edit `_data/team.yml`:
```yaml
- name: "James R. Faeder"
  role: "Principal Investigator"
  email: "faeder@pitt.edu"
  bio: "Your bio here..."
  orcid: "https://orcid.org/YOUR-ORCID-ID"
```

### 5. Push to GitHub (3 min)
```bash
cd "/Users/faeder/Library/CloudStorage/OneDrive-UniversityofPittsburgh/Code/Website"
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git
git push -u origin main
```

### 6. Enable GitHub Pages (2 min)
```
1. Go to repository Settings → Pages
2. Source: Select "GitHub Actions"
3. Wait 2-3 minutes
4. Visit https://YOUR-USERNAME.github.io/REPO-NAME/
```

## Done! 🎉

Your site is live! Now you can:
- Edit content directly on GitHub (no coding required)
- Have lab members add their profiles
- Update research and publications as needed

## Common URLs

**User Site:**
- Repo: `https://github.com/USERNAME/USERNAME.github.io`
- Live: `https://USERNAME.github.io/`

**Project Site:**
- Repo: `https://github.com/USERNAME/faeder-lab`
- Live: `https://USERNAME.github.io/faeder-lab/`

## What to Edit First

1. **_config.yml** - Site settings and your info
2. **_data/team.yml** - Your profile
3. **index.md** - Home page content
4. **research.md** - Research areas
5. **publications.md** - Your publications

## Getting Help

- Full documentation: [README.md](README.md)
- Detailed setup: [SETUP.md](SETUP.md)
- Contributing guide: [CONTRIBUTING.md](CONTRIBUTING.md)

## Pro Tips

✅ Edit files directly on GitHub - no software needed!
✅ Changes go live in 2-3 minutes automatically
✅ Preview markdown with the "Preview" tab
✅ Use clear commit messages
✅ Keep your ORCID profile updated for automatic publications

---

**Need help?** See SETUP.md for detailed instructions and troubleshooting.
