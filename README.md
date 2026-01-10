# Faeder Lab Website

A modern, easy-to-maintain lab website built with Jekyll and hosted on GitHub Pages. All content is managed through simple markdown files that anyone in the lab can edit.

## Quick Start for Lab Members

### Editing Content

All content is stored in markdown files. To edit:

1. Navigate to the file you want to edit
2. Click the pencil icon (Edit this file)
3. Make your changes
4. Scroll down and click "Commit changes"
5. The website will automatically update in a few minutes

### Common Editing Tasks

#### Update Home Page
Edit `index.md` to change the home page content, hero section, and highlights.

#### Add/Edit Research Content
Edit `research.md` to update research areas and descriptions.

#### Update Publications
Edit `publications.md` to add new publications. For the most up-to-date list, make sure your ORCID profile is current.

#### Add/Remove Team Members

1. Open `_data/team.yml`
2. Copy the template for a new member
3. Fill in the details:
   - `name`: Full name
   - `role`: One of: "Principal Investigator", "Postdoctoral Researcher", "PhD Student", "Undergraduate Student", "Research Staff", "Alumni"
   - `image`: Path to photo (upload to `assets/images/team/`)
   - `bio`: Short description (1-2 sentences)
   - `email`: Email address
   - `github`, `twitter`, `orcid`: Optional social/academic links
   - `order`: Number for sorting (lower numbers appear first)

4. Upload their photo to `assets/images/team/`

#### Update Photos

To add or update photos:

1. Go to `assets/images/` (or `assets/images/team/` for team photos)
2. Click "Add file" → "Upload files"
3. Drag and drop your image
4. Commit the changes
5. Update the relevant markdown file to reference the new image path

## Local Development

To run the site locally for testing:

### Prerequisites

- Ruby (2.7 or higher)
- Bundler (`gem install bundler`)

### Setup

```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME

# Install dependencies
bundle install

# Run the local server
bundle exec jekyll serve

# Open http://localhost:4000 in your browser
```

The site will automatically reload when you make changes to files.

## Setting Up GitHub Pages

### Initial Setup

1. **Create a GitHub repository**
   - Go to https://github.com/new
   - Name it `faeder-lab` (or whatever you prefer)
   - Make it public
   - Don't initialize with README (we already have one)

2. **Push your code**
   ```bash
   cd /path/to/Website
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository settings
   - Click "Pages" in the left sidebar
   - Under "Source", select "main" branch
   - Click "Save"
   - Your site will be available at `https://YOUR-USERNAME.github.io/REPO-NAME/`

4. **Update configuration**
   - Edit `_config.yml`
   - Update `url` to `https://YOUR-USERNAME.github.io`
   - Update `baseurl` to `/REPO-NAME` (or leave empty if using a user site)
   - Update social media handles and ORCID ID
   - Commit and push changes

### Using a Custom Domain (Optional)

1. In your repository settings → Pages
2. Enter your custom domain (e.g., `faederlab.org`)
3. Create a `CNAME` file in the root with your domain name
4. Update your DNS settings (see [GitHub docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site))

## Project Structure

```
.
├── _config.yml           # Site configuration
├── _layouts/             # HTML templates
│   ├── default.html      # Base template
│   ├── home.html         # Home page template
│   └── page.html         # Standard page template
├── _includes/            # Reusable components
│   └── team-member.html  # Team member card
├── _data/                # Data files
│   └── team.yml          # Team member information
├── assets/               # Static files
│   ├── css/
│   │   └── style.scss    # Main stylesheet
│   └── images/           # Images
│       └── team/         # Team photos
├── index.md              # Home page content
├── research.md           # Research page
├── team.html             # Team page
├── publications.md       # Publications page
└── README.md             # This file
```

## Customization

### Changing Colors

Edit `assets/css/style.scss` and modify the color variables at the top:

```scss
$primary-color: #2563eb;    // Main theme color
$secondary-color: #0891b2;  // Secondary accent
$accent-color: #f59e0b;     // Highlights
```

### Changing Fonts

Fonts are loaded from Google Fonts. To change them:

1. Edit `_layouts/default.html`
2. Update the Google Fonts link
3. Edit `assets/css/style.scss` and update `$font-primary` and `$font-secondary`

### Adding New Pages

1. Create a new markdown file (e.g., `software.md`)
2. Add front matter:
   ```yaml
   ---
   layout: page
   title: Software
   description: Lab software and tools
   ---
   ```
3. Add your content below the front matter
4. Add the page to navigation in `_config.yml`

## Getting Help

- **Jekyll Documentation**: https://jekyllrb.com/docs/
- **GitHub Pages Documentation**: https://docs.github.com/en/pages
- **Markdown Guide**: https://www.markdownguide.org/

For lab-specific questions, contact the lab web administrator or open an issue in the repository.

## Tips for Collaboration

### For Lab Members Without Git Experience

The easiest way to contribute is directly through GitHub's web interface:

1. Navigate to the file on GitHub
2. Click the pencil icon to edit
3. Make your changes
4. Write a brief description of what you changed
5. Click "Commit changes"

### For Lab Members With Git Experience

```bash
# Create a branch for your changes
git checkout -b update-research-page

# Make your changes
# ...

# Commit and push
git add .
git commit -m "Update research descriptions"
git push origin update-research-page

# Create a pull request on GitHub for review
```

## License

This website template is available for use by academic labs. The content is © Faeder Lab.
