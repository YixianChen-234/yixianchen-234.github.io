---
layout: about
title: Home
permalink: /
subtitle: Research Scientist, <a href='https://geography.ua.edu/'>Department of Geography and the Environment</a>, The University of Alabama · <a href='https://sdml.ua.edu/'>Surface Dynamics Modeling Lab</a>

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>Department of Geography and the Environment</p>
    <p>The University of Alabama</p>
    <p>Tuscaloosa, AL 35401, USA</p>
    <p><a href="mailto:ychen223@ua.edu">ychen223@ua.edu</a></p>
    <p class="cv-download"><a href="/assets/pdf/cv.pdf" target="_blank" rel="noopener"><i class="fa-solid fa-file-pdf"></i>&nbsp;Curriculum Vitae</a></p>
    <p class="profile-socials">
    <a href="https://scholar.google.com/citations?user=CVTiODEAAAAJ" title="Google Scholar" aria-label="Google Scholar" rel="external nofollow noopener" target="_blank"><i class="ai ai-google-scholar"></i></a>
    <a href="https://www.linkedin.com/in/yixian-chen-765583166" title="LinkedIn" aria-label="LinkedIn" rel="external nofollow noopener" target="_blank"><i class="fa-brands fa-linkedin"></i></a>
    <a href="https://github.com/YixianChen-234" title="GitHub" aria-label="GitHub" rel="external nofollow noopener" target="_blank"><i class="fa-brands fa-github"></i></a>
    <a href="https://www.researchgate.net/profile/Yixian-Chen-8/" title="ResearchGate" aria-label="ResearchGate" rel="external nofollow noopener" target="_blank"><i class="ai ai-researchgate"></i></a>
    <a href="https://orcid.org/0000-0002-7710-580X" title="ORCID" aria-label="ORCID" rel="external nofollow noopener" target="_blank"><i class="ai ai-orcid"></i></a>
    </p>

selected_papers: false # set true to list papers marked selected={true} in the bibliography
social: false # social icons are shown under the profile photo instead (profile-socials above); keep in sync with _data/socials.yml

announcements:
  enabled: true # includes a list of news items
  scrollable: false # show all items without an inner scroll bar
  limit: # blank = include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<style>
  /* Tighten vertical spacing in the landing-page news list. Scoped to this page
     so no gem SCSS is shadowed and theme updates still apply. */
  .news table { margin-bottom: 0.5rem; }
  .news table td,
  .news table th { padding-top: 0.4rem; padding-bottom: 0.4rem; line-height: 1.45; }
  .news table td p,
  .news table th p { margin-bottom: 0; }

  /* Selected publications block on this page uses the same markup as
     /publications/, so mirror those overrides here. */
  .publications .author em {
    font-style: normal;
    font-weight: 700;
  }
  .publications h2.bibliography {
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--global-text-color);
    padding-top: 0.6rem;
    margin-top: 1.2rem;
  }

  /* Journal abbreviation badges removed; collapse the now-empty left column
     so entries use the full row width. */
  .publications ol.bibliography .col-sm-2.abbr { display: none; }
  .publications ol.bibliography .col-sm-8 { flex: 0 0 100%; max-width: 100%; }

  /* Education / Experience lists */
  .cv-list { margin: 0.2rem 0 0.6rem; }
  .cv-item { display: flex; gap: 1.1rem; padding: 0.55rem 0; border-bottom: 1px solid var(--global-divider-color); }
  .cv-item:last-child { border-bottom: none; }
  .cv-when { flex: 0 0 9.5rem; font-size: 0.84rem; color: var(--global-text-color-light); padding-top: 0.15rem; }
  .cv-what { flex: 1 1 auto; line-height: 1.5; }
  .cv-org { color: var(--global-text-color); }
  .cv-note { font-size: 0.87rem; color: var(--global-text-color-light); }
  /* A concurrent appointment nested under its parent entry, as in the CV. */
  .cv-concurrent { margin-top: 0.35rem; padding-left: 0.75rem; border-left: 2px solid var(--global-divider-color); }
  @media (max-width: 576px) {
    .cv-item { flex-direction: column; gap: 0.15rem; }
    .cv-when { flex: none; }
  }

  /* CV download link under the profile block */
  .cv-download { margin-top: 0.35rem; }
  .cv-download a { font-size: 0.9rem; }
  .cv-download i { color: var(--global-theme-color); }

  /* Social icons under the profile photo (replaces the theme's bottom row). */
  /* Selector matches the theme's `.profile .more-info p` margin reset so the top margin applies. */
  .profile .more-info p.profile-socials { display: flex; flex-wrap: wrap; gap: 0.9rem; margin-top: 0.9rem; font-size: 1.6rem; line-height: 1; }
  .profile-socials a { color: var(--global-text-color); text-decoration: none; }
  .profile-socials a:hover { color: var(--global-theme-color); }
</style>

I study how water reshapes land, and how to make that predictable at scale. At the [Surface Dynamics Modeling Lab](https://sdml.ua.edu/) I work on **flood inundation mapping (FIM)** for [CIROH](https://ciroh.ua.edu/), a NOAA cooperative institute, on how the U.S. operational flood model represents river channels and floodplains: I bring satellite measurements of river slope from NASA's ICESat-2 and SWOT missions onto the model's river network with a [spatial joining framework](https://github.com/sdmlua/riverjoin_py) I built, track how river slope changes through time, and study which channel and floodplain attributes should be calibrated together for different places and flood sizes. My longer-running work is on **gully erosion**, the cutting of deep channels into hillslopes and valleys by concentrated runoff during heavy rain: how gullies form and develop, what controls their morphology and density, and how they respond to extreme rainstorms and vegetation restoration &mdash; from field and remote-sensing measurement on the Chinese Loess Plateau to [modelling gully occurrence worldwide](https://esdac.jrc.ec.europa.eu/content/global-patterns-gully-occurrence).

## Experience

<div class="cv-list" markdown="0">
<div class="cv-item">
  <div class="cv-when">Apr 2026 &ndash; present</div>
  <div class="cv-what"><strong>Research Scientist</strong><br>
  <span class="cv-org">The University of Alabama</span>, USA<br>
  <span class="cv-note">Optimal synthetic rating curve calibration for U.S. operational flood inundation mapping</span></div>
</div>
<div class="cv-item">
  <div class="cv-when">May 2024 &ndash; Mar 2026</div>
  <div class="cv-what"><strong>Postdoctoral Fellow</strong><br>
  <span class="cv-org">The University of Alabama</span>, USA<br>
  <span class="cv-note">Improving spatial and temporal river slope data for U.S. operational flood inundation mapping</span></div>
</div>
<div class="cv-item">
  <div class="cv-when">Mar 2021 &ndash; Apr 2024</div>
  <div class="cv-what"><strong>Postdoctoral Researcher</strong><br>
  <span class="cv-org">Northwest University</span>, China<br>
  <span class="cv-note">Morphological characteristics and volume estimating models of gullies on the Chinese Loess Plateau</span>
  <div class="cv-concurrent">Concurrently <strong>Postdoctoral Researcher</strong>, <span class="cv-org">KU Leuven</span>, Belgium, Jul 2022 &ndash; Jun 2023<br>
  <span class="cv-note">Data-driven prediction of gully densities at the global scale</span></div></div>
</div>
</div>

## Education

<div class="cv-list" markdown="0">
<div class="cv-item">
  <div class="cv-when">2014 &ndash; 2021</div>
  <div class="cv-what"><strong>Ph.D. in Soil Science</strong><br>
  <span class="cv-org">University of Chinese Academy of Sciences</span>, China<br>
  <span class="cv-note">Dissertation: Morphological spatial variation and development mechanisms of gullies on the Chinese Loess Plateau</span></div>
</div>
<div class="cv-item">
  <div class="cv-when">2019 &ndash; 2020</div>
  <div class="cv-what"><strong>Visiting Ph.D. Researcher</strong><br>
  <span class="cv-org">University of Li&egrave;ge</span>, Belgium<br>
  <span class="cv-note">Sub-continental gully density prediction using machine learning</span></div>
</div>
<div class="cv-item">
  <div class="cv-when">2010 &ndash; 2014</div>
  <div class="cv-what"><strong>B.S. in Soil and Water Conservation and Desertification Control</strong><br>
  <span class="cv-org">Guizhou University</span>, China</div>
</div>
</div>
