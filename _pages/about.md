---
layout: about
title: about
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

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I study how water reshapes land, and how to make that predictable at scale.

My work runs along one line, from gully erosion on the Chinese Loess Plateau to the river-slope layer inside the operational flood inundation mapping system of the United States. The methods travel: take a geomorphic process that has only been described qualitatively, make it predictable, and ship the result as something other people can build on.

At the [Surface Dynamics Modeling Lab](https://sdml.ua.edu/) I work on **flood inundation mapping (FIM)** for [CIROH](https://ciroh.ua.edu/), a NOAA cooperative institute. I diagnosed and replaced the poorly represented river slope layer in NOAA's operational HAND-FIM system: satellite measurements of river slope already existed, from NASA's ICESat-2 and SWOT missions, but nothing carried them onto the river network the model runs on. The [spatial joining framework](https://github.com/sdmlua/riverjoin_py) I built to bridge that gap made the transfer possible, and the improved slopes are now the first-priority input to the operational model, worth an average 31% gain in flood-map accuracy across eight U.S. flood events.

I am currently **Lead PI on a $300,000 NOAA CIROH project** asking a follow-on question: improving one model parameter in isolation can unbalance an existing calibration, so which combination of channel and floodplain attributes should be calibrated, for which flood magnitudes, in which places?

Earlier, and still ongoing, I work on **gully erosion** — a widespread driver of land degradation and an under-represented geo-hydrological hazard. I led the [first global assessment of gully occurrence](https://esdac.jrc.ec.europa.eu/content/global-patterns-gully-occurrence), built from 17,499 sites interpreted from high-resolution satellite imagery and modelled with a random forest ensemble at 1 km² resolution. The maps are archived by the European Commission's Joint Research Centre, and the work has been covered by the [BBC](https://www.bbc.co.uk/news/resources/idt-61d57e25-d458-4785-8a37-3ef119a504c7).

The thread connecting these is a habit rather than a topic: I try not to look at one variable in isolation. Studying erosion after a 200-year rainstorm, I measured every process rather than only the one I came for — and found that the terraces and check dams built to *prevent* erosion had become the second-largest sediment source once they failed.

I am always glad to hear from people working on flood risk, river hydrology, erosion, or Earth-observation data products. The best way to reach me is [email](mailto:ychen223@ua.edu).
