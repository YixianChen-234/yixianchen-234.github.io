---
layout: page
title: Global river slope variability from SWOT
description: Monthly, reach-level water-surface slopes worldwide — because river slope is not static.
img:
importance: 5
category: flood
---

Operational flood models treat river slope as a fixed property. It is not: water-surface slope varies with discharge, season, and channel change, and treating it as constant discards information that satellites can now supply.

Using **Hydrocron**, NASA's SWOT time-series service, I collected every available observation worldwide between August 2023 and May 2025, queried against SWOT River Database (SWORD v16) reach identifiers. For each reach I extracted water-surface slope, elevation, width, and detected area — **together with their uncertainty estimates and reach quality flags**, so the resulting product carries its own error budget.

The result is a global, monthly, reach-level water-surface slope dataset, published on [Zenodo](https://doi.org/10.5281/zenodo.17926443), and the basis for supplying time-corresponding rather than static slope to flood inundation models.
