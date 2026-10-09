---
layout: default
title: Home
---
<section class="hero">
  <div class="wrapper">
    <h1 class="hero-question">What happens when AI stops being a tool and starts being a <span class="chalk-underline">colleague</span>?</h1>
    <p class="hero-intro">I am a technologist, and I write about AI and agentic systems and what they mean for organisations and the people who work in them.</p>
  </div>
</section>

<section class="section">
  <div class="wrapper">
    <h2 class="section-label">Series</h2>
    <ul class="series-grid">
{%- assign visible_series = site.data.series | where: "visible", true -%}
{%- for series in visible_series %}
      <li>
        <a class="series-card" href="{{ series.url | relative_url }}">
          <div class="series-card-board">{{ series.title | escape }}</div>
          <div class="series-card-body">
            <p>{{ series.description | escape }}</p>
            <span class="series-card-more">Read the series<span class="doodle-arrow" aria-hidden="true"></span></span>
          </div>
        </a>
      </li>
{%- endfor %}
    </ul>
  </div>
</section>

<section class="section">
  <div class="wrapper">
    <h2 class="section-label">Latest articles</h2>
{%- assign latest = site.pages | where: "layout", "article" | sort: "date" | reverse -%}
{%- if latest.size > 0 %}
    <ul class="article-list">
{%- for article in latest limit: 5 %}
{%- assign s = site.data.series | where: "id", article.series | first %}
      <li>
        <a href="{{ article.url | relative_url }}">{{ article.title | escape }}</a>
        <span class="article-meta">{{ s.title | escape }}{% if article.part %} · Part {{ article.part }}{% endif %} · {{ article.date | date: "%-d %B %Y" }}</span>
      </li>
{%- endfor %}
    </ul>
{%- else %}
    <p class="empty-note">The first article is coming soon.</p>
{%- endif %}
  </div>
</section>
