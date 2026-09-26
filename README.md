# Aki Uddin — Portfolio

A static portfolio site for Aki Uddin, mechanical engineering student at the University of Michigan.

Everything on the site is driven by two things: `data/projects.json` (identity, skills, involvement, project cards) and the markdown files in `content/projects/` (the full case study pages). You can update the whole site without touching HTML.

## Run it locally

The site fetches JSON and markdown, so opening `index.html` directly from the filesystem will not work in most browsers. Serve it instead:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Structure

```
index.html              Home page (hero, about, skills, projects, involvement, resume, contact)
project.html            Case study template — reads ?slug=<name> from the URL
data/projects.json      Owner info, skills, involvement, and project card data
content/projects/*.md   Case study content, one file per project slug
resume.pdf              Resume, embedded in the Resume section and offered as a download
js/main.js              Home page rendering, theme toggle, search and tag filters
js/project.js           Case study rendering (markdown + front matter)
images/                 Photos and CAD renders
```

## Adding or editing a project

1. Add an entry to the `projects` array in `data/projects.json`. The `slug` is the key that links everything together.
2. Create `content/projects/<slug>.md` with YAML front matter at the top (copy the format from an existing file).
3. Drop any images in `images/` and reference them as `images/your-file.jpg` from the markdown.
4. Add the new URL to `sitemap.xml`.

A project with no matching markdown file still gets a card; the case study page just shows "content is not available yet."

## Current projects

| Slug | Project |
| --- | --- |
| `adaptive-controller` | Adaptive Controller for Hemiparesis — ENGR 100 team project (PlayMakers) |
| `custom-controller` | Custom 3D-Printed Game Controller — ENGR 100 individual build |
| `chem-e-car` | Chem-E-Car Chassis — ongoing student team work |

## Things to add later

- **Phone number.** The resume header has no phone number. Add one in `Aki_Uddin_Resume.tex` (there is a commented placeholder) and recompile.
- **Portfolio URL on the resume.** Once this site is deployed, uncomment the portfolio link line in `Aki_Uddin_Resume.tex` and recompile.
- **Headshot.** The hero image currently uses `images/controller_hero.jpg`. Swap `owner.photo` in `data/projects.json` to a real headshot when there is one.
- **Chem-E-Car photos and detail.** `content/projects/chem-e-car.md` is intentionally short because the work is ongoing.
- **GitHub link.** `owner.github` is empty, so the GitHub button is removed from the contact section at runtime. Fill it in to bring the button back.

## Deploying to GitHub Pages

1. Push this folder to a GitHub repository.
2. In repository Settings → Pages, set the source to the `main` branch, root folder.
3. Update the URLs in `sitemap.xml` and `robots.txt` to the real site address.

`.nojekyll` is already present so GitHub Pages serves every file as-is.

## Resume

`resume.pdf` is built from LaTeX. The source lives at `~/Desktop/career/resumes/Aki_Uddin_Resume.tex`. To change it:

```bash
cd ~/Desktop/career/resumes && tectonic -X compile Aki_Uddin_Resume.tex
```

Then copy the new `Aki_Uddin_Resume.pdf` over `resume.pdf` in this folder. The site shows a download prompt instead of the viewer if the file is missing.

## Credits

Project photos, CAD renders, and written content come from Aki's ENGR 100 coursework: the individual controller submission and the PlayMakers team final report, *Adaptive Controller for Hemiparesis* (Emmanuel Fafalios, Julius Stephens, Aki Uddin), submitted April 21, 2026.
