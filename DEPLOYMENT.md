# Deployment Guide

## Test locally first

The site loads `data/projects.json` and the files in `content/projects/` over `fetch`, so opening `index.html` straight from Finder will show an empty page. Serve the folder instead:

```bash
python3 -m http.server 8000
```

Open http://localhost:8000 and check:

- Hero name, title, and the four stat tiles render
- All three project cards appear, and search and tag filters work
- Each "Read case study" link opens `project.html` with images and the table of contents
- The Involvement grid lists all six entries
- The Resume section embeds `resume.pdf` and the download button works
- The dark/light toggle works on both pages

## Deploy to GitHub Pages

1. Push this folder to a GitHub repository.
2. Repository Settings -> Pages -> Source: `main` branch, `/ (root)`.
3. The site goes live at `https://<username>.github.io/<repository-name>`.
4. Update the URLs in `sitemap.xml` and `robots.txt` to match that address.

`.nojekyll` is already in the folder, which stops GitHub Pages from running Jekyll and skipping files.

## Content checklist

- [x] `resume.pdf` added at the root (rebuild from `~/Desktop/career/resumes/Aki_Uddin_Resume.tex`)
- [ ] Phone number added to the resume header, and the portfolio link uncommented once deployed
- [ ] Real headshot added and `owner.photo` updated in `data/projects.json`
- [ ] `owner.github` filled in if there is a GitHub profile to link
- [ ] Chem-E-Car case study expanded with photos as the work progresses
- [ ] `sitemap.xml` and `robots.txt` URLs point at the real domain

## Before you publish

- The ENGR 100 user is referred to only by the first name used in the course report. Keep it that way.
- Confirm the two Google Doc links in `data/projects.json` are shared appropriately, since the project pages link to them publicly.
- Run the site through Google PageSpeed Insights and check it at phone width.
