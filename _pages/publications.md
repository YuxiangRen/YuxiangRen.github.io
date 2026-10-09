---
layout: academic
title: "Publications"
permalink: /publications/
body_class: page-publications
publication_filters: true
---

<p class="publication-intro">You can also find my articles on <a href="{{ site.author.googlescholar }}">my Google Scholar profile</a>.</p>

{% assign publications = site.publications | sort: 'cv_order' %}
{% assign publication_years = publications | group_by_exp: 'post', "post.date | date: '%Y'" | sort: 'name' | reverse %}
{% assign conference_papers = publications | where: 'kind', 'conference' %}
{% assign journal_papers = publications | where: 'kind', 'journal' %}
<p>{{ publications.size }} publications · {{ conference_papers.size }} conference papers · {{ journal_papers.size }} journal papers</p>
<p class="subtle">* Equal contribution · ♢ Corresponding author</p>

<form id="publication-filters" class="pub-controls" role="search" aria-label="Filter publications" hidden>
  <label for="pub-search">Search publications
    <input id="pub-search" type="search" placeholder="Title, author, or venue" autocomplete="off">
  </label>
  <label for="pub-year">Year
    <select id="pub-year">
      <option value="">All years</option>
      {% for group in publication_years %}<option value="{{ group.name }}">{{ group.name }}</option>{% endfor %}
    </select>
  </label>
</form>
<div class="filter-status" hidden>
  <span id="result-count" role="status" aria-live="polite"></span>
  <button id="reset-filter" type="button" class="reset-filter" hidden>Reset filters</button>
</div>
<nav class="year-nav" aria-label="Publication years">
  {% for group in publication_years %}<a href="#year-{{ group.name }}">{{ group.name }}</a>{% endfor %}
</nav>

{% for group in publication_years %}
<section class="pub-year" id="year-{{ group.name }}" aria-labelledby="heading-{{ group.name }}">
  <h2 id="heading-{{ group.name }}">{{ group.name }}</h2>
  <ul class="pub-list">
    {% for post in group.items %}{% include academic-publication.html %}{% endfor %}
  </ul>
</section>
{% endfor %}
<p class="no-results" id="no-results" hidden>No publications match your search.</p>
