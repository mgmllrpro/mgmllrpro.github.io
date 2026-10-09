---
layout: default
title: Home
---

What happens when AI stops being a tool and starts being a colleague?
I am a technologist, and I write about AI and agentic systems and what they
mean for organisations and the people who work in them.

## Series

<ul class="series-list">
{%- assign visible_series = site.data.series | where: "visible", true -%}
{%- for series in visible_series %}
  <li>
    <h3><a href="{{ series.url | relative_url }}">{{ series.title | escape }}</a></h3>
    <p>{{ series.description | escape }}</p>
  </li>
{%- endfor %}
</ul>

## Latest articles

{% assign latest = site.pages | where: "layout", "article" | sort: "date" | reverse %}
{% if latest.size > 0 %}
<ul class="article-list">
{%- for article in latest limit: 5 %}
  {%- assign s = site.data.series | where: "id", article.series | first %}
  <li>
    <a href="{{ article.url | relative_url }}">{{ article.title | escape }}</a>
    <span class="article-meta">{{ s.title | escape }} · {{ article.date | date: "%-d %B %Y" }}</span>
  </li>
{%- endfor %}
</ul>
{% else %}
*The first article is coming soon.*
{% endif %}
