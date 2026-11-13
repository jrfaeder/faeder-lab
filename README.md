# Faeder Lab website

Built with Greene Lab's [Lab Website Template](https://github.com/greenelab/lab-website-template) (v1.4.1; [docs](https://greene-lab.gitbook.io/lab-website-template-docs)).
Jekyll site, deployed to GitHub Pages by GitHub Actions.

## Common edits

| To change… | Edit |
|---|---|
| A lab member (add, update, photo) | `_members/<first-last>.md`; photos go in `images/team/` (square, ~700 px) |
| Someone leaves the lab | Delete their `_members/` file and add them to `_data/alumni.yaml` |
| News | Add `_posts/YYYY-MM-DD-short-title.md` |
| Software list | `_data/projects.yaml` (`group: featured` puts a tool in the top row) |
| Highlighted papers, or descriptions/tags on papers | `_data/sources.yaml` (use the DOI exactly as ORCID stores it, including case) |
| Research text | `research/index.md` |
| Colors | `_styles/-theme.scss` |

**Publications are automatic.** They come from James Faeder's ORCID record (`_data/orcid.yaml`).
GitHub Actions regenerates `_data/citations.yaml` weekly and on every push, so never edit that file by hand.
`_cite/cite.py` has a small lab customization that removes Web of Science placeholders and preprint/published duplicates.
To hide a paper, add `- id: <doi>` with `remove: true` to `_data/sources.yaml`.

Member roles: `principal-investigator`, `postdoc`, `phd`, `masters`, `undergrad` (defined in `_data/types.yaml`).

## Previewing locally

Use Ruby 3.4 (CI uses 3.4; Ruby 4.0 currently breaks the `jekyll-spaceship` plugin).

```bash
bundle install
bundle exec jekyll serve      # http://localhost:4000
```

Regenerating citations locally needs Python with `pip install -r _cite/requirements.txt`, and `manubot` on your PATH:

```bash
python _cite/cite.py
```
