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

selected_papers: false # set true to list papers marked selected={true} in the bibliography
social: true # includes social icons at the bottom of the page

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

  /* Contact icons: stack a label under each, and label them properly
     (the plugin's own titles read "Scholar userid", "Orcid id", ...). */
  .contact-icons { display: flex; flex-wrap: wrap; justify-content: center; gap: 1.1rem; }
  .contact-icons a {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 0.3rem;
    text-decoration: none;
  }
  .contact-icons a::after {
    font-size: 0.68rem;
    line-height: 1;
    color: var(--global-text-color-light);
    white-space: nowrap;
  }
  .contact-icons a[href*="scholar.google"]::after { content: "Google Scholar"; }
  .contact-icons a[href*="linkedin"]::after       { content: "LinkedIn"; }
  .contact-icons a[href*="github"]::after         { content: "GitHub"; }
  .contact-icons a[href*="researchgate"]::after   { content: "ResearchGate"; }
  .contact-icons a[href*="orcid"]::after          { content: "ORCID"; }

  /* contact_note is empty; drop the element so it leaves no gap. */
  .contact-note:empty { display: none; }
</style>

I study how water reshapes land, and how to make that predictable at scale.

My work runs along one line, from gully erosion on the Chinese Loess Plateau to the river-slope layer inside the operational flood inundation mapping system of the United States. The methods travel: take a geomorphic process that has only been described qualitatively, make it predictable, and ship the result as something other people can build on.

At the [Surface Dynamics Modeling Lab](https://sdml.ua.edu/) I work on **flood inundation mapping (FIM)** for [CIROH](https://ciroh.ua.edu/), a NOAA cooperative institute. I diagnosed and replaced the poorly represented river slope layer in NOAA's operational HAND-FIM system: satellite measurements of river slope already existed, from NASA's ICESat-2 and SWOT missions, but nothing carried them onto the river network the model runs on. The [spatial joining framework](https://github.com/sdmlua/riverjoin_py) I built to bridge that gap made the transfer possible, and the improved slopes are now the first-priority input to the operational model, worth an average 31% gain in flood-map accuracy across eight U.S. flood events.

I am currently **Lead PI on a $300,000 NOAA CIROH project** asking a follow-on question: improving one model parameter in isolation can unbalance an existing calibration, so which combination of channel and floodplain attributes should be calibrated, for which flood magnitudes, in which places?

Earlier, and still ongoing, I work on **gully erosion** — a widespread driver of land degradation and an under-represented geo-hydrological hazard. I led the [first global assessment of gully occurrence](https://esdac.jrc.ec.europa.eu/content/global-patterns-gully-occurrence), built from 17,499 sites interpreted from high-resolution satellite imagery and modelled with a random forest ensemble at 1 km² resolution. The maps are archived by the European Commission's Joint Research Centre, and the work has been covered by the [BBC](https://www.bbc.co.uk/news/resources/idt-61d57e25-d458-4785-8a37-3ef119a504c7).
