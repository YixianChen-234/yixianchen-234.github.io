---
layout: page
permalink: /publications/
title: Publications
description: Publications by categories in reversed chronological order.
nav: true
nav_order: 2
---

<style>
  /* First-authored entries (lead = true in papers.bib) are listed first, then the rest;
     each list is sorted by year and month. The counter is reset on the container so
     numbering runs on across both lists. */
  #pub-articles { counter-reset: pubnum 36; }
  .publications ol.bibliography {
    list-style: none;
    padding-left: 0;
  }
  .publications ol.bibliography > li {
    counter-increment: pubnum -1;
    display: flex;
    gap: 0.5rem;
    margin-bottom: 0.65rem;
    line-height: 1.5;
  }
  .publications ol.bibliography > li::before {
    content: counter(pubnum) ".";
    flex: 0 0 2.1rem;
    text-align: right;
    color: var(--global-text-color-light);
  }
  .pub-entry { flex: 1 1 auto; }
  .pub-authors strong { font-weight: 700; text-decoration: underline; text-underline-offset: 2px; }
  .pub-title { color: var(--global-theme-color); }
  .pub-title:hover { text-decoration: underline; }
  .pub-venue { font-style: italic; }
  .pub-note { color: var(--global-text-color-light); font-size: 0.9em; }
  .publications ol.bibliography { margin-bottom: 0; }
</style>

<!-- _pages/publications.md -->

{% include bib_search.liquid %}

<div class="publications" id="pub-articles">
{% bibliography --query @article[lead=true] %}
{% bibliography --query @article[lead!=true] %}
</div>
