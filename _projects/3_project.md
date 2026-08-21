---
layout: page
title: Global patterns of gully occurrence
description: The first global assessment of gully head density and susceptibility, at 1 km² resolution.
img:
importance: 3
category: erosion
related_publications: true
---

Gully erosion is a major driver of soil loss and land degradation worldwide, and an under-represented geo-hydrological hazard — yet before this work there was no global picture of where gullies occur, or of what controls them.

**Building the training data.** Machine learning at this scale is bottlenecked by labelled observations, not by algorithms. I designed a rapid scoring scheme — each 1 km² site scored 0, 1–5, 6–20, or more than 20 gully heads from high-resolution satellite imagery, in one to two minutes — and generated a global training set of **17,499 sites**: 12,005 randomly located across the land surface, plus 5,494 targeted in regions of particular interest. Repeat interpretation of the same sites agreed at r² = 0.95.

**Modelling.** A 100-model random forest ensemble over 26 predictor variables spanning topography, soil, land cover and climate, trained and applied on HPC, published together with an explicit uncertainty layer showing where the ensemble disagrees.

**Findings.** Global gully patterns arise from non-linear interactions among environmental factors, with strong regional variation in which factor dominates. Hotspots sensitive to human drivers include the Chinese Loess Plateau, the Ethiopian Highlands, and large parts of the Mediterranean and Sahel. Deserts also show high gully densities, but there the cause is natural rather than anthropogenic — a distinction with real land-management consequences.

The maps are archived in the European Commission's [European Soil Data Centre](https://esdac.jrc.ec.europa.eu/content/global-patterns-gully-occurrence), and the work was covered by [BBC News](https://www.bbc.co.uk/news/resources/idt-61d57e25-d458-4785-8a37-3ef119a504c7).
