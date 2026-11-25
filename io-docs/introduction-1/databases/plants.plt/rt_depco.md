---
description: Root depth rate coefficient for perennial plants
---

# rt\_depco

**Code reference:** `pldb(ic)%rt_depco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L93), [default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L28)).

Column 50. Coefficient of the exponential root-depth equation used for plants that are not annuals (default 0.2; values ≤ 0 are replaced by 0.2). [`pl_root_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_root_gro.f90#L22-L28) sets:

$$
z_{root} = 1000\,z_{max}\left(1 - e^{-k\,y}\right)
$$

where:

- $z_{root}$ is the root depth (mm),
- $z_{max}$ is [rt\_dp\_max](untitled-7.md) (m),
- $k$ is `rt_depco` (1/year), and
- $y$ is the plant's current years toward maturity (years).

Annual plants use a heat-unit equation instead, so this column has no effect on them.

In SWAT+ main this column held `frac_sw_gro`, which was read but not used. A file with the older 54-column layout gets the default 0.2 here.
