# suryaportfolio — updated site

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The new site. Single file — all CSS and JS inline, no jQuery, no Bootstrap. |
| `suryakiranchallagulla.html` | Identical copy, so your existing URL keeps working. |
| `images/optimized/` | Re-compressed WebP versions of your existing images (4.6 MB → 364 KB). |
| `Surya-Kiran-Challagulla-Resume.pdf` | Your resume, linked from the nav and the contact section. |
| `.gitignore` | Ignores `.DS_Store` — there are 10 of them committed in the repo right now. |

Your original `images/`, `css/`, `fonts/` and `js/` folders are untouched. The new page
doesn't reference `css/`, `fonts/` or `js/` at all, so you can delete those three later
once you're happy with the result — that drops about 14 MB from the repo.

## Deploy

Drop these files into your `suryaportfolio` checkout, keeping the folder structure
(`images/optimized/` goes inside your existing `images/`), then:

```bash
cd suryaportfolio
find . -name .DS_Store -not -path "./.git/*" -delete
git add -A
git commit -m "Rebuild portfolio: new UI, resume updates through Aug 2026"
git push
```

## Turn on GitHub Pages

Settings → Pages → Source: **Deploy from a branch** → branch `main`, folder `/ (root)`.

`index.html` is the default document, so the site serves at
`https://surya-kiran-challagulla.github.io/suryaportfolio/`.

## Editing it later

Everything lives in `index.html`. The parts you're most likely to touch:

- **Colors** — the `:root` block at the very top. `--volt` is the accent; change that one
  value and the whole site re-tints.
- **Experience** — search for `<article class="role">`. Copy one block to add a job.
- **Projects** — search for `<a class="card"`. Each card is one block. `<span class="yr">`
  is the date badge, `<span class="tag">` is the category pill. Cards with a real repo are
  `<a>`; the two without a repo are `<div>`.
- **Stats** — search for `data-count`. The number counts up to that value when it scrolls
  into view.
- **Hero name** — search for `hero-type`. The three giant lines auto-shrink to fit the
  screen, so longer text won't break the layout.

## Notes on the content

Work history now follows the resume you sent: Mr. Cooper (Oct 2024 – Present) and Infosys
(Oct 2019 – Dec 2021), plus the UMBC teaching assistant role. The old Zendesk and Infosys
intern entries are gone.

Project dates come from the actual first-commit dates on your GitHub repos:
Distributed File System (May 2022), Microsoft Malware Detection (Dec 2023),
apidemo (Oct 2024), Client-Server Token Manager (Jul 2024). The two projects with no repo
— Spark IPL analysis and Driver Drowsiness Detection — have no date badge, since I had no
verifiable date for them. Add one if you know it.

The old site described you as a data analyst ("converting complex data into actionable
insights", Power BI–heavy skills list). That's been replaced with the engineering profile
from your resume.
