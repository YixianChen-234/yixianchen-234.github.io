---
layout: page
title: riverjoin
description: An open-source framework for joining river flowlines across heterogeneous hydrographic datasets.
img:
importance: 2
category: software
---

Hydrographic datasets — digital representations of river-network geometry and topology — are fundamental to hydrologic modelling, but they disagree with one another on flowline density, length, spatial offset, and network topology. Those disagreements block interoperability, and they were the reason satellite river-slope measurements could not reach the operational flood model.

`riverjoin` links flowlines across heterogeneous datasets despite those differences and transfers attributes in both directions. It can join **any** two linear river networks that carry basic connectivity fields — a unique reach ID and its downstream neighbour — so nothing in it is specific to one dataset pair.

The workflow has five steps: buffer-zone candidate search, downstream tracing to recover missed flowlines, perpendicular transects for the most-upstream and otherwise missed reaches, bifurcation handling, and final alignment with attribute transfer along evenly spaced points.

**Demonstrated dataset pairs:** HAND-FIM ↔ SWORD · HAND-FIM ↔ IRIS · HAND-FIM ↔ GEOGLOWS · SWORD ↔ GEOGLOWS · SWORD ↔ MERIT Basins · SWORD ↔ GRIT.

It also powers GEOGLOWS-driven flood mapping in FIMserv, extending operational-grade flood inundation mapping beyond the United States.

- [PyPI](https://pypi.org/project/riverjoin/) · [GitHub](https://github.com/sdmlua/riverjoin_py)
