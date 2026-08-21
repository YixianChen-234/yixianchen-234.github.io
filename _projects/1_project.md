---
layout: page
title: Operational river slope for U.S. flood mapping
description: Satellite-derived river slopes now the first-priority input to NOAA's HAND-FIM, worth an average 31% gain in flood-map accuracy.
img:
importance: 1
category: flood
related_publications: true
---

**The problem.** River slope drives the synthetic rating curves inside NOAA's operational flood inundation mapping system (OWP HAND-FIM). Those slopes were computed from the national 3DEP digital elevation model, which is hydroconditioned to guarantee downstream flow. That conditioning, combined with the genuinely flat gradients of real rivers, produced many erroneous slope values — and because a national DEM cannot realistically be updated often, the slopes were static.

**The approach.** Better measurements already existed, from NASA's ICESat-2 laser altimetry (the IRIS dataset) and the SWOT mission, but they were described against a different river network than the operational model uses. I built a spatial joining framework to reconcile the two, which is what allowed the satellite observations to reach the model at all.

**The outcome.** Improved slopes were merged into [NOAA-OWP/inundation-mapping](https://github.com/NOAA-OWP/inundation-mapping/pull/1505) in May 2025 as the **first-priority** slope source, ahead of the NWM hydrofabric and the legacy DEM computation. Across eight U.S. flood events benchmarked against high-precision flood maps, mapping accuracy improved by an average of **31%** (Critical Success Index). Two products were released: FIM HF IRIS and NextGen HF IRIS.

**Artifacts**
- Paper: *Scientific Data* 12, 1657 (2025)
- Data: [Zenodo](https://doi.org/10.5281/zenodo.21632749) · [HydroShare](https://doi.org/10.4211/hs.1532f4cb360244f9a6ba772ebd428180)
- Coverage: [CIROH news](https://awi.ua.edu/2025/09/26/new-satellite-derived-river-slope-database-helps-improves-u-s-flood-forecasts/)
