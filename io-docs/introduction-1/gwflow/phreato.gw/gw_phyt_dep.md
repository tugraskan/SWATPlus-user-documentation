---
description: "Water-table depth below ground, m"
---

# gw_phyt_dep

**Code reference:** `gw_phyt_dep(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L432), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1431)).

Depth of the water table below the ground surface, in m, at which the rate on the same line applies. List depths in increasing order. For a water-table depth between two points, the rate is interpolated linearly ([`gwflow_phreatophyte.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_phreatophyte.f90#L31-L37)):

$$w = z - h$$

where $w$ is the water-table depth below ground (m), $z$ is the ground elevation (m), and $h$ is the groundwater head (m).

$$r = r_{k} - \frac{w - w_{k}}{w_{k+1} - w_{k}} \, (r_{k} - r_{k+1})$$

where:
- $r$ is the interpolated phreatophyte transpiration rate (`m/day`),
- $r_{k}$ and $r_{k+1}$ are the tabulated rates at bracketing points $k$ and $k+1$ (`m/day`),
- $w$ is the water-table depth below ground (m), and
- $w_{k}$ and $w_{k+1}$ are the bracketing `gw_phyt_dep` values (m).

Shallower than the first depth or deeper than the last, the rate is 0.
