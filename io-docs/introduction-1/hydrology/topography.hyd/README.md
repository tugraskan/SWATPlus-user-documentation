---
description: >-
  This file defines the topographic characteristics of the HRUs and Routing
  Units.
---

# topography.hyd

Each record supplies topographic parameters referenced by HRUs and routing units. After the title and header, [`topo_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topo_read.f90#L31-L52) reads each record in the order below.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the topography record | string | n/a | n/a | n/a |
| [slp](slp.md) | Average slope steepness | real | m/m | 0.02 |  |
| [slp\_len](slp_len.md) | Average slope length | real | m | 50.0 |  |
| [lat\_len](lat_len.md) | Average slope length for lateral subsurface flow | real | m | 50.0 |  |
| [dist\_cha](dist_cha.md) | Average distance to stream (stored for calibration) | real | m |  |  |
| [depos](depos.md) | Sediment transport capacity multiplier | real | none | 1 |  |
