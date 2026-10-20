---
layout: page
title: Optimal synthetic rating curve calibration for U.S. flood inundation mapping
description: NOAA CIROH FY26 · PI · $300K total (UA and USU) · 2026–2027
img:
importance: 1
category: grants
---

**Role:** PI · **Funder:** NOAA Cooperative Institute for Research to Operations in Hydrology (CIROH), FY26 · **Award:** $300,000 USD total, covering The University of Alabama and Utah State University · **Period:** July 2026 – March 2027

Flood inundation mapping in NOAA's operational HAND-FIM framework depends on synthetic rating curves (SRCs), and those curves inherit every weakness in the channel data behind them: missing or simplified bathymetry, spatially uniform roughness, and uncertain river slope. This project starts from a result of my earlier work — that improving a _single_ SRC parameter in isolation can introduce new errors elsewhere, because the existing calibration was balanced around the old values.

The project develops a sensitivity-informed framework that recommends and applies the most suitable SRC calibration scenario for a given reach and event. We test **eleven calibration scenarios** combining improved channel and floodplain attributes — geometry, river slope, spatially varying channel and floodplain roughness, and topographically derived calibration points — together with CONUS-scale SRC adjustment factors.

Using **FIMbench**, a benchmark flood inundation dataset, and reach-scale evaluation across approximately **1,000 benchmark samples**, we train scenario-performance models that recommend reach-level calibration based on event magnitude and local topographic, hydrologic, and land-cover conditions. Scenario maps are generated with **FIMserv** and scored with **FIMeval**.

**Planned outputs:** curated SRC scenario outputs and evaluation datasets, scenario-performance models, and an updated FIMserv release with automated calibration recommendation — disseminated through CIROH platforms, the NOAA CIROH Developers Conference, and the National Water Center Summer Institute.
