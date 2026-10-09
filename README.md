# Thinking Ahead

Articles by Michael, a technologist thinking beyond the technology: what AI and
agentic systems mean for organisations and the people who work in them.
Read them on the website: **https://mgmllrpro.github.io**

Views are my own and do not necessarily reflect those of my employer.

---

## Repository structure

```
├── index.md                      Start page: series and latest articles
├── about.md                      About page
├── _config.yml                   Site settings
├── _data/series.yml              List of all series (title, description, visible)
├── _layouts/                     Page templates for series and articles
├── _includes/article-list.html   Automatic article list per series
├── assets/                       Styles and shared images
├── agentic-operating-model/
│   ├── index.md                  Series overview (fills itself)
│   └── 01-<article-slug>/
│       ├── index.md              The article
│       └── header.png            Header image, also used for LinkedIn previews
└── cyber-resilience/
    └── index.md                  Prepared series (not yet published)
```

## Publishing an article

1. Create a folder `<series>/<NN>-<article-slug>/` (via **Add file → Upload files**, drag in the folder).
2. It contains `index.md` with this front matter, followed by the article text:

   ```yaml
   ---
   layout: article
   title: "Article title"
   description: "One or two sentences – shown in overviews and LinkedIn previews."
   series: agentic-operating-model
   part: 2
   date: 2026-11-03
   image: /agentic-operating-model/02-article-slug/header.png
   ---
   ```

3. Add `header.png` (1200 × 627 px works best for LinkedIn).
4. Commit. The series page, the start page and the navigation update automatically.

## Starting a new series

1. Set `visible: true` for the series in `_data/series.yml` (or add a new entry).
2. Create `<series>/index.md` with `layout: series` and `series: <id>`.
3. Optionally add it to `header_pages` in `_config.yml` to show it in the top navigation.

## License

Text and images: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) unless stated otherwise.
