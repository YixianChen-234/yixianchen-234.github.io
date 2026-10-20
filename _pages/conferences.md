---
layout: page
permalink: /conferences/
title: Conferences
description: Conference presentations, posters, and invited talks.
nav: true
nav_order: 3
---

<style>
  /* First-authored entries (lead = true in papers.bib) are listed first, then the rest;
     each list is sorted by year and month. The counter is reset on the container so
     numbering runs on across both lists. */
  #pub-confs { counter-reset: pubnum 19; }
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
  .pub-cat {
    font-size: 1.05rem;
    font-weight: 700;
    margin: 1.8rem 0 0.7rem;
    padding-bottom: 0.3rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .pub-cat:first-child { margin-top: 0.6rem; }
  .pub-cat-note { font-size: 0.85rem; color: var(--global-text-color-light); margin: -0.35rem 0 0.8rem; }
</style>

<div class="publications" id="pub-confs">
<h2 class="pub-cat">First-authored</h2>
{% bibliography --query @inproceedings[lead=true] %}
<h2 class="pub-cat">Co-authored</h2>
{% bibliography --query @inproceedings[lead!=true] %}
</div>
