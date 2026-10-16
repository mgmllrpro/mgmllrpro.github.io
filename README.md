# Beyond the Technology

What happens when AI stops being a tool and starts doing the work?
Articles on AI and agentic systems and what they mean for organisations and
the people who work in them.
Read them on the website: **https://mgmllrpro.github.io**

Views are my own and do not necessarily reflect those of my employer.

---

## Repository structure

```
├── index.md                      Start page: series and latest articles
├── about.md                      About page
├── _config.yml                   Site settings
├── _data/series.yml              List of all series (title, description, visible, parts, related)
├── _layouts/                     Page templates for series and articles
├── _includes/article-list.html   Automatic article list (series without parts)
├── _includes/series-toc.html     Table of contents from the parts in _data/series.yml
├── _includes/tldr.html           TL;DR box for articles and series pages
├── assets/                       Styles and shared images
├── agentic-operating-model/
│   ├── index.md                  Series overview: TL;DR, how to read, contents
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
   tldr:
     - "Three short statements the reader should take away."
     - "One sentence each."
     - "Shown as the TL;DR box at the top, with the reading time."
   ---
   ```

3. Add `header.png` (1200 × 627 px works best for LinkedIn).
4. Commit. The series page, the start page and the navigation update automatically;
   in the table of contents the part turns from "Coming soon" into a link.

## Writing tips

Every article starts with a **TL;DR**: three statements in the front matter (`tldr:`). The
layout shows them as a light card with a chalk accent above the header image, together with
the reading time (about 230 words per minute). Series pages have their own `tldr:` and
`tldr_meta:` and show the box as a dark chalkboard.


Highlight a key idea with the light bulb box – write a quote and add the class
directly below it:

```markdown
> Agents don't replace the operating model – they force us to make it explicit.
{: .key-idea}
```

Use it at most once or twice per article so it keeps its effect.

Set background information apart with the callout box – a quote whose first line is the
label, with the class directly below. It is used, for example, for the box
"On Microsoft's platform" after a vendor-neutral explanation:

```markdown
> **On Microsoft's platform**
>
> Two services cover much of this. …
{: .callout}
```

## Starting a new series

1. Set `visible: true` for the series in `_data/series.yml` (or add a new entry).
2. Create `<series>/index.md` with `layout: series` and `series: <id>`.
3. Optionally add it to `header_pages` in `_config.yml` to show it in the top navigation.

## License

Text and images: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) unless stated otherwise.
