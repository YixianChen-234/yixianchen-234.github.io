---
layout: page
permalink: /research/
title: Research Highlights
description: Selected work on flood inundation mapping and soil erosion.
nav: true
nav_order: 1
---

<style>
  /* Stacked layout: text on top, figures in a single row beneath. */
  .rh-block { margin: 3.4rem 0 5rem; }
  .rh-text { min-width: 0; }
  .rh-block h3 { font-size: 1.205rem; font-weight: 700; margin: 0 0 0.4rem; }
  .rh-cite { font-size: 0.86rem; color: var(--global-text-color-light); margin-bottom: 0.6rem; }
  .rh-cite .rh-me { color: var(--global-text-color); font-weight: 700; text-decoration: underline; text-underline-offset: 2px; }
  .rh-body { line-height: 1.6; }

  .rh-fig {
    display: flex;
    flex-wrap: wrap;
    gap: 1.25rem;
    align-items: flex-start;
    margin-top: 1.1rem;
  }
  .rh-fig figure {
    flex: 1 1 0;
    min-width: 240px;
    margin: 0;
    text-align: center;
  }
  .rh-fig img { max-width: 100%; height: auto; border-radius: 8px; }

  /* When a row holds more than one figure, give them a common height. Width is
     left to follow each image's own aspect ratio, so nothing is cropped,
     stretched, or letterboxed — the figures simply sit on a shared baseline. */
  .rh-fig--multi { align-items: flex-start; flex-wrap: nowrap; }
  .rh-fig--multi figure { min-width: 0; }   /* flex-grow is set inline, = aspect ratio */
  .rh-fig--multi img { width: 100%; height: auto; }

  /* Split row: a stacked column beside a single tall figure. Column flex values
     are set inline from the images' aspect ratios so both sides finish level. */
  .rh-fig--split .rh-col { display: flex; flex-direction: column; min-width: 0; }
  .rh-fig--split .rh-col > figure + figure { margin-top: 4%; }
  .rh-fig--split figure { margin: 0; }
  .rh-fig--split { flex-wrap: wrap; align-items: flex-start; }
  .rh-rowcap { flex: 1 0 100%; font-size: 0.78rem; color: var(--global-text-color-light);
               margin-top: 0.5rem; line-height: 1.4; text-align: left; }

  /* Fig 7 was recomposed to Fig 5's exact panel geometry (same canvas width,
     same axis positions), so both render at full column width and their three
     panels line up column-for-column. */
  @media (max-width: 700px) {
    .rh-fig--split { flex-wrap: wrap; }
    .rh-fig--split .rh-col { flex: 1 1 100% !important; }
  }
  @media (max-width: 700px) {
    .rh-fig--multi { flex-wrap: wrap; }
    .rh-fig--multi figure { flex: 1 1 100% !important; }
  }
  /* A single near-square figure would otherwise span the full column and
     dominate the block; cap it and centre it. */
  .rh-fig figure.rh-half { max-width: 62%; margin-left: auto; margin-right: auto; }
  .rh-fig figure.rh-tall { max-width: 50%; margin-left: auto; margin-right: auto; }
  @media (max-width: 700px) { .rh-fig figure.rh-half { max-width: 100%; } }

  .rh-fig figcaption {
    font-size: 0.78rem;
    color: var(--global-text-color-light);
    margin-top: 0.45rem;
    line-height: 1.4;
    text-align: left;
  }

  .rh-sec { margin-top: 2.6rem; border-bottom: 1px solid var(--global-divider-color); padding-bottom: 0.3rem; }
</style>

<h2 class="rh-sec">Flood</h2>

<div class="rh-block">
  <div class="rh-text">
    <h3>Improved river slope for the U.S. operational flood model</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, Cohen S, Baruah A, Devi D, Dhital S, Tian D, Munasinghe D (2025). <em>Scientific Data</em> 12, 1657. <a href="https://doi.org/10.1038/s41597-025-05941-6">DOI</a> · <a href="https://doi.org/10.5281/zenodo.21632749">data</a></div>
    <div class="rh-body">River slope drives the synthetic rating curves inside NOAA's operational HAND-FIM system, but those slopes came from a hydroconditioned national DEM that cannot resolve the near-flat gradients of real rivers &mdash; and, being static, could not track change. I replaced them with slopes from NASA's ICESat-2 laser altimetry (IRIS), supplemented by SWORD.<br><br>The improved slopes raised flood-map accuracy by an average of <strong>31%</strong> (Critical Success Index) across eight U.S. flood events, and were merged into <code>NOAA-OWP/inundation-mapping</code> in May 2025, where the operational system still uses them.</div>
  </div>
  <div class="rh-fig rh-fig--multi">
    <figure style="flex: 0.9725 1 0"><img src="{{ '/assets/img/research/improved-slope-1.webp' | relative_url }}" width="1556" height="1600" decoding="async" data-zoom-src="{{ '/assets/img/research/improved-slope-1.png' | relative_url }}" alt="Improved river slope for the U.S. operational flood model"><figcaption>Satellite-derived river slopes (a) versus the original HAND-FIM slopes (b) across the United States.</figcaption></figure>
    <figure style="flex: 1.4210 1 0"><img src="{{ '/assets/img/research/improved-slope-2.webp' | relative_url }}" width="1600" height="1126" decoding="async" data-zoom-src="{{ '/assets/img/research/improved-slope-2.png' | relative_url }}" alt="Improved river slope for the U.S. operational flood model"><figcaption>Flood extent for three events using original, satellite and NextGen slopes, scored against a remote-sensing benchmark.</figcaption></figure>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>riverjoin &mdash; making satellite data reach operational models</h3>
    <div class="rh-cite">Open-source Python package. <a href="https://github.com/sdmlua/riverjoin_py">GitHub</a> · <a href="https://pypi.org/project/riverjoin/">PyPI</a></div>
    <div class="rh-body">Hydrographic datasets disagree on flowline density, length, spatial offset and network topology, and that is precisely why better satellite measurements could not be attached to the operational river network. <code>riverjoin</code> reconciles them: it joins <strong>any</strong> two linear river networks given only geometry and basic connectivity fields, and transfers attributes in both directions.<br><br>Demonstrated across six dataset pairs &mdash; HAND-FIM &harr; SWORD, IRIS and GEOGLOWS; SWORD &harr; GEOGLOWS, MERIT Basins and GRIT &mdash; from catchment to global scale. It also powers GEOGLOWS-driven flood mapping in FIMserv, extending operational-grade flood inundation mapping beyond the United States.</div>
  </div>
  <div class="rh-fig rh-fig--multi">
    <figure style="flex: 0.9125 1 0"><img src="{{ '/assets/img/research/riverjoin-1.webp' | relative_url }}" width="1460" height="1600" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/riverjoin-1.png' | relative_url }}" alt="riverjoin - making satellite data reach operational models"><figcaption>The riverjoin matching workflow: buffer search, downstream tracing, then transects.</figcaption></figure>
    <figure style="flex: 0.8156 1 0"><img src="{{ '/assets/img/research/riverjoin-2.webp' | relative_url }}" width="1305" height="1600" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/riverjoin-2.png' | relative_url }}" alt="riverjoin - making satellite data reach operational models"><figcaption>GEOGLOWS flowlines matched to SWORD worldwide, with Mississippi, Amazon and Congo insets.</figcaption></figure>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>Temporal variability of global river slope from SWOT</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, Cohen S, Dhital S, Devi D, Baruah A (2026). <em>Geophysical Research Letters</em>, under revision. <a href="https://doi.org/10.5281/zenodo.17926443">data</a></div>
    <div class="rh-body">Operational models treat river slope as a fixed property, but water-surface slope varies with discharge, season and channel change. Using <strong>Hydrocron</strong>, NASA's SWOT time-series service, I collected every available observation worldwide between August 2023 and May 2025, queried against SWORD v16 reach identifiers.<br><br>For each reach I extracted water-surface slope, elevation, width and detected area <strong>together with their uncertainty estimates and quality flags</strong> &mdash; producing a global, monthly, reach-level slope dataset that carries its own error budget, and the basis for supplying time-corresponding rather than static slope to flood models.</div>
  </div>
  <div class="rh-fig">
    <figure><img src="{{ '/assets/img/research/temporal-slope-1.webp' | relative_url }}" width="2400" height="1014" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/temporal-slope-1-zoom.webp' | relative_url }}" alt="Temporal variability of global river slope from SWOT"><figcaption>Relative variability of water-surface slope worldwide from SWOT.</figcaption></figure>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>Optimal synthetic rating curve calibration</h3>
    <div class="rh-cite">NOAA CIROH FY26 · PI · $300K total · 2026&ndash;2027</div>
    <div class="rh-body">NOAA's operational HAND-FIM system turns National Water Model flow forecasts into flood maps through a <strong>synthetic rating curve</strong> for every river reach &mdash; a computed link between flow and water level, built from the channel's shape, slope and roughness and calibrated against observed floods. Better versions of those inputs now exist, but improving one in isolation can make the calibrated model worse, because the calibration was balanced around the old values &mdash; something I found while validating the river slope work. This project tests <strong>eleven calibration scenarios</strong> combining improved riverbed shape (bathymetry), slope and land-cover-based roughness, and trains models that recommend the best calibration for each reach, evaluated over roughly <strong>1,000 reach-scale benchmark samples</strong>.<br><br>First results from three benchmark floods show that the answer depends on the place and the event &mdash; <strong>no single calibration wins everywhere</strong>. In Conway, Arkansas, land-cover-based roughness raised map accuracy by 18% and halved false alarms compared with the current operational calibration; in Goldsboro, North Carolina, improved bathymetry gained 11% even though the operational model already did well there. Stacking every improvement at once raised accuracy but inflated false alarms &mdash; the trade-off that makes a per-reach recommendation necessary.</div>
  </div>
  <div class="rh-fig">
    <figure><img src="{{ '/assets/img/research/src-calibration-1.webp' | relative_url }}" width="1800" height="604" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/src-calibration-1.png' | relative_url }}" alt="Preliminary SRC calibration results for three benchmark floods"><figcaption>Preliminary results for three benchmark floods. For each calibration scenario: map accuracy as the Matthews correlation coefficient (MCC, blue; higher is better) and the false positive rate (FPR, orange; dry land wrongly mapped as flooded, lower is better). Dashed lines mark the current operational calibration (OWP HAND-FIM v4.8).</figcaption></figure>
  </div>
</div>

<h2 class="rh-sec">Soil Erosion</h2>

<div class="rh-block">
  <div class="rh-text">
    <h3>Can gullies be trusted from satellite imagery?</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, Jiao J, Wei Y, Zhao H, Yu W, Cao B (2019). <em>International Journal of Environmental Research and Public Health</em> 16(3), 369.</div>
    <div class="rh-body">Most gully studies interpret morphology from high-resolution imagery without first testing whether the imagery represents gullies accurately. Before mapping gullies at regional scale, I measured how well it works.<br><br>Using Pleiades-1B imagery at 0.5 m panchromatic resolution, gully planform can be interpreted accurately overall: larger gullies are captured more accurately, more complex planforms less so, and winter imagery is largely unaffected by vegetation. From field-measured gully area and perimeter I built correction models &mdash; R&sup2; = 0.99 for area and R&sup2; = 0.98 for perimeter (n = 130) &mdash; which made the regional work that followed defensible.</div>
  </div>
  <div class="rh-fig rh-fig--multi">
    <figure style="flex: 1.4042 1 0"><img src="{{ '/assets/img/research/gully-accuracy-1.webp' | relative_url }}" width="1400" height="997" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/gully-accuracy-1.png' | relative_url }}" alt="Graphical abstract"><figcaption>Graphical abstract: assessing how accurately gully planform can be interpreted from high-resolution imagery.</figcaption></figure>
    <figure style="flex: 1.4271 1 0"><img src="{{ '/assets/img/research/gully-accuracy-2.webp' | relative_url }}" width="1350" height="946" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/gully-accuracy-2.png' | relative_url }}" alt="Figure 8"><figcaption>Two cases that reduce interpretation accuracy: dense vegetation cover (a) and high, overhanging gully scarps (b).</figcaption></figure>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>Gully morphology and density along a rainfall gradient</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, Jiao J, Yan X, Li J, Vanmaercke M, Wang N (2024). <em>Catena</em> 236, 107773.</div>
    <div class="rh-body">Gully research on the Chinese Loess Plateau had concentrated on individual gullies and small watersheds. This study asked how gully morphology and density vary across the whole region, and what controls that variation.<br><br>Gully dimensions increase from north to south &mdash; width most of all &mdash; under the joint influence of rainfall and the slope of the contributing drainage area. Number, length and area densities all decrease as vegetation cover rises, and number density matters more than gully size in setting overall density. Rainy-season rainfall and vegetation cover emerge as the dominant regional controls, with rainfall's indirect effect through vegetation outweighing its direct effect on gully occurrence.</div>
  </div>
  <div class="rh-fig">
    <figure><img src="{{ '/assets/img/research/gully-morph-fig3.webp' | relative_url }}" width="1800" height="308" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/gully-morph-fig3.png' | relative_url }}" alt="Figure 3"><figcaption>Remote-sensing imagery and interpreted gully edges across the five study catchments.</figcaption></figure>
  </div>

  <div class="rh-fig rh-fig--multi rh-fig--split">
    <div class="rh-col" style="flex: 0.8429 1 0">
      <figure><img src="{{ '/assets/img/research/gully-morph-fig5.webp' | relative_url }}" width="1600" height="477" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/gully-morph-fig5.png' | relative_url }}" alt="Figure 5"></figure>
      <figure><img src="{{ '/assets/img/research/gully-morph-fig7.webp' | relative_url }}" width="1600" height="477" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/gully-morph-fig7.png' | relative_url }}" alt="Figure 7"></figure>
    </div>
    <div class="rh-col" style="flex: 0.6006 1 0">
      <figure><img src="{{ '/assets/img/research/gully-morph-fig6.webp' | relative_url }}" width="1400" height="1261" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/gully-morph-fig6.png' | relative_url }}" alt="Figure 6"></figure>
    </div>
    <figcaption class="rh-rowcap">Gully length, width and depth (top left); number, length and area density (bottom left); and length&ndash;width ratio, width&ndash;depth ratio, area and volume (right), across the five study catchments.</figcaption>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>Gully development before the Grain-for-Green programme</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, Jiao J, Wei Y, Zhao H (2017). <em>Transactions of the Chinese Society of Agricultural Engineering</em> 33(17), 120&ndash;127. EI-indexed, in Chinese. <a href="https://doi.org/10.11975/j.issn.1002-6819.2017.17.016">DOI</a></div>
    <div class="rh-body">To judge whether a restoration programme worked, you need a credible baseline for what came before it. This study characterised gully development in the Northern Shaanxi hilly loess region over 1976&ndash;1997, prior to the Grain-for-Green programme.<br><br>In that period valley erosion was driven by widening, gully head retreat and the formation of new gullies together &mdash; a markedly more active regime than what followed. It provides the reference against which later reductions in head retreat and valley growth are measured, and underpins the long-term assessment of vegetation restoration.</div>
  </div>
  <div class="rh-fig rh-fig--multi">
    <figure style="flex: 1.3611 1 0"><img src="{{ '/assets/img/research/grainforgreen-1.webp' | relative_url }}" width="1700" height="1249" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/grainforgreen-1.png' | relative_url }}" alt="Valley area change 1976-1997"><figcaption>Valley area of the seven large gullies in 1976 and 1997, showing widening, headward erosion and newly formed small gullies.</figcaption></figure>
    <figure style="flex: 1.5116 1 0"><img src="{{ '/assets/img/research/grainforgreen-2.webp' | relative_url }}" width="1300" height="860" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/grainforgreen-2.png' | relative_url }}" alt="Correlation with vegetation coverage"><figcaption>Correlation with vegetation coverage in the upslope catchment. Filled markers are significant at <em>P</em> &lt; 0.05.</figcaption></figure>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>Catchment-scale erosion contributions of different processes</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, Vanmaercke M, Jiao J, Bai L, Tang B, Wang N, Zhang Y, Wang H (2023). <em>Land Degradation &amp; Development</em> 34(2), 403&ndash;422. <a href="https://doi.org/10.1002/ldr.4468">DOI</a></div>
    <div class="rh-body">After a rainstorm with an estimated 200-year return period struck Zizhou County in July 2017, I went to study gully erosion &mdash; and measured every other process as well. That decision produced the result.<br><br>Landsliding contributed 4,433 &plusmn; 657 t km<sup>&minus;2</sup> (37 &plusmn; 4%) and the <strong>collapse of terraces and check dams 3,927 &plusmn; 1,009 t km<sup>&minus;2</sup> (33 &plusmn; 4%)</strong>, ahead of rill erosion (24 &plusmn; 3%) and gully erosion (7 &plusmn; 4%). The engineered erosion controls, once they failed, were the second-largest sediment source in the catchment &mdash; many failures traceable to maintenance gaps and design choices rather than to the storm alone. The low gully contribution is the mirror-image finding: evidence that vegetation restoration has worked.</div>
  </div>
  <div class="rh-fig rh-fig--multi">
    <figure style="flex: 0.9549 1 0"><img src="{{ '/assets/img/research/rainstorm-fig6.webp' | relative_url }}" width="1419" height="1486" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/rainstorm-fig6.jpg' | relative_url }}" alt="Erosion observations on new terraces"><figcaption>Erosion on new terraces: (a) overview; (b) collapse along a terrace cut-slope; (c) embankment breach at concave sections; (d) rills and gullies on the terrace field; (e) rills and gullies on the connecting road.</figcaption></figure>
    <figure style="flex: 1.3318 1 0"><img src="{{ '/assets/img/research/rainstorm-fig8.webp' | relative_url }}" width="1421" height="1067" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/rainstorm-fig8.jpg' | relative_url }}" alt="Three main cases of check-dam failure"><figcaption>Three main cases of check-dam failure: (a) spillway and (b) nearby dam-body collapse from clogged or undersized drainage holes; (c) spillway collapse from limited flood-release capacity; (d) dam-body collapse where no flood-release facility existed.</figcaption></figure>
    <figure style="flex: 1.3026 1 0"><img src="{{ '/assets/img/research/rainstorm-1.webp' | relative_url }}" width="1003" height="770" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/rainstorm-1.png' | relative_url }}" alt="Total erosion intensity and composition"><figcaption>Total erosion intensity and its composition in the three catchments. Collapsed conservation structures (light blue) rival the natural processes; the big dam alone contributed 23,199 t km<sup>&minus;2</sup> in QSG.</figcaption></figure>
  </div>
</div>

<div class="rh-block">
  <div class="rh-text">
    <h3>The first global map of gully occurrence</h3>
    <div class="rh-cite"><span class="rh-me">Chen Y</span>, De Geeter S, Poesen J, Matthews F, Campforts B, Borrelli P, Panagos P, Vanmaercke M (2026). <em>International Soil and Water Conservation Research</em> 14, 100572. <a href="https://doi.org/10.1016/j.iswcr.2025.09.004">DOI</a> · <a href="https://esdac.jrc.ec.europa.eu/content/global-patterns-gully-occurrence">ESDAC</a></div>
    <div class="rh-body">Gully erosion drives land degradation worldwide, but no global picture existed of where gullies occur or what controls them. The bottleneck was labelled data, not algorithms.<br><br>I designed a rapid scoring scheme &mdash; each 1 km&sup2; site scored from high-resolution satellite imagery in one to two minutes &mdash; and generated a global training set of <strong>17,499 sites</strong>, with repeat interpretation agreeing at r&sup2; = 0.95. A <strong>100-model random forest ensemble</strong> over 26 environmental predictors then mapped gully head density and susceptibility at 1 km&sup2; resolution, published with an explicit uncertainty layer.<br><br>Anthropogenically sensitive hotspots include the Chinese Loess Plateau, the Ethiopian Highlands, and much of the Mediterranean and Sahel. Deserts also show high gully densities, but there the cause is natural &mdash; a distinction with direct consequences for land management.</div>
  </div>
  <div class="rh-fig rh-fig--multi">
    <figure style="flex: 1.5106 1 0"><img src="{{ '/assets/img/research/globalgully-1.webp' | relative_url }}" width="1500" height="993" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/globalgully-1.png' | relative_url }}" alt="Impacts of gully erosion"><figcaption>Why gullies matter: land loss, damage to buildings and roads, sediment supply to rivers, runoff connectivity and flood risk, and downstream reservoir effects.</figcaption></figure>
    <figure style="flex: 0.7707 1 0"><img src="{{ '/assets/img/research/globalgully-2.webp' | relative_url }}" width="1156" height="1500" loading="lazy" decoding="async" data-zoom-src="{{ '/assets/img/research/globalgully-2.png' | relative_url }}" alt="Observed and simulated gully occurrence worldwide"><figcaption>Observed gully head density at the 17,499 interpreted sites (a), simulated density (b), and simulated susceptibility (c), at 1 km&sup2; resolution.</figcaption></figure>
  </div>
</div>

<style>
  .rh-fig img { cursor: zoom-in; }
  .medium-zoom-overlay { z-index: 1000; }
  .medium-zoom-image--opened { z-index: 1001; }
</style>

<script>
  // medium-zoom ships with the theme but is not bound on this page.
  // Bind it to the research figures: click expands the full-resolution image
  // over a dark overlay; click again, press Esc, or scroll to dismiss.
  window.addEventListener("load", function () {
    if (typeof mediumZoom === "undefined") return;
    mediumZoom(document.querySelectorAll(".rh-fig img"), {
      background: "rgba(0, 0, 0, 0.92)",
      margin: 24,
    });
  });
</script>
