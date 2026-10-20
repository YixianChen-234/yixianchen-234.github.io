---
layout: page
permalink: /conferences/
title: Conferences
description: Conference presentations, posters, and invited talks.
nav: true
nav_order: 3
---

<style>
  #pub-confs ol.bibliography { counter-reset: pubnum 19; }
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
</style>

<div class="publications" id="pub-confs">
{% bibliography --query @inproceedings %}
</div>
