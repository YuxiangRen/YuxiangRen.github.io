# Yuxiang Ren's personal website

Jekyll academic homepage for Yuxiang Ren (任宇翔), Nanjing University.
The presentation follows the shared purple LINK Lab style of the
[reference homepage](https://github.com/liujiaheng/liujiaheng.github.io).
Biography, recruitment, news, publications, CV, portrait, and personal links
come from this repository, not from the reference site's content.

## Edit content

- `_pages/about.md`: biography, recruitment, research interests, all 48 news
  entries, followed by Education and Experience.
- `_publications/*.md`: publication titles, authors, dates, venues, citations,
  and paper links. Each publication must have its own `permalink`.
- `_data/cv.yml`: profile, education, experience, 5 courses, 8 projects, and
  10 patents from the October 9, 2026 CV. Prior website details are retained
  when they are not superseded by the new source. Education and experience
  render on About; other CV details remain available in the downloadable PDF
  and this data file.
- `_config.yml`: personal profile, contact links, and site URL.
- `_data/navigation.yml`: top navigation.
- `_data/members.yml`: 1 postdoctoral researcher, 2 Ph.D. students,
  2 master’s students, and 11 previously mentored students. Records combine
  CV PDF pages 6–8 with member additions and role updates supplied by the
  site owner. Unspecified periods and affiliations are left blank.
  Cooperation references link to the corresponding papers.
- `_data/services.yml`: standards drafting, editorial board, and conference /
  journal reviewing from CV PDF pages 8–9.
- `_data/honors.yml`: 16 honors, combining CV PDF page 2 with the existing
  web CV. Source labels are retained in the data, including both distinct
  FSU travel-funding entries from 2020 and 2021.
- `images/profile.jpg` and `files/`: the original portrait and paper downloads.
  `files/renyuxiangCV.pdf` is the unmodified October 9, 2026 CV supplied by the
  user, replacing the old CV at the same URL.

The public routes `/`, `/publications/`, `/about/`, and `/about.html` are
retained. There is no standalone CV page or CV navigation item; `/cv/` and
`/resume` redirect to About for older links. Three previously colliding
publication routes now have distinct URLs. Bibliographic content is synchronized
with the latest user-provided CV, and all existing paper download links are kept. The existing Metric and GDiffRetro routes remain in use.
Members, Services, and Honors use the reference template's paths
`/group.html`, `/service.html`, and `/award.html`, with their own content from
this repository's CV. Edit their presentation in `_pages/members.html`,
`_pages/services.html`, and `_pages/honors.html`.

## Latest CV synchronization

Source: the user-provided `中文简历__主页_ (1).pdf`, updated October 9, 2026.
The source PDF is copied without altering its pages or content. Earlier news,
recruitment information, institutional email, social links, and website-only
honors are retained.

The bibliography contains 37 records (31 conference papers and 6 journal
papers), identified by `cv_id` (`C1`–`C31`, `J1`–`J6`) and ordered by `cv_order`.
These references also drive mentoring links. The six added papers have only
a publication year in the source: their January 1 `date` is an internal Jekyll
placeholder (`date_precision: year`); the website displays the year only.
No paper URLs or publication months were inferred. CCF/SCI labels and author
contribution marks are transcribed from the supplied CV, not independently
reassessed. Coauthor names that also appear in the design reference are
retained only where they are explicitly present in the user's CV.

Services and honors are maintained on their respective pages. The About page
retains the Full CV PDF download. These links keep `/files/renyuxiangCV.pdf` and
add a version derived from `_data/cv.yml` to refresh cached downloads.

## Run locally

```sh
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

For a production build:

```sh
bundle exec jekyll build
```

Continue deploying as a Jekyll site on GitHub Pages. Do not add `.nojekyll`:
this adaptation retains the original Markdown collections and Liquid layouts.
No client-side framework or npm build is needed for the new presentation.

## Presentation and attribution

- `_layouts/academic.html`, `_layouts/home.html`, and
  `_layouts/publication.html`: shared page shell, profile, and paper details.
- `assets/css/academic.css`: shared reference styles.
- `assets/css/personal.css`: adjustments for the original square portrait,
  bilingual recruitment text, education, and experience.
- `assets/js/publications.js`: optional search and year filters. All papers
  and links remain accessible without JavaScript.

See [THIRD_PARTY.md](THIRD_PARTY.md) for the source revision and license notices.
