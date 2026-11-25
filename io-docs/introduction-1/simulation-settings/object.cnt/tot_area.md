---
description: Total area of the watershed in ha
---

# tot\_area

**Code reference:** `bsn%area_tot_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L12)).

Total watershed area including ponds and reservoirs (`ha`; Fortran struct default: `0.`). Read in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38), it is used to area-weight basin aquifer outputs in [`basin_aquifer_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aquifer_output.f90#L20):

$$w = \frac{A_{\text{aqu}}}{A_{\text{tot}}}$$

where $w$ is the basin aquifer area-weighting factor (dimensionless), $A_{\text{aqu}}$ is the aquifer area (ha), and $A_{\text{tot}}$ is `tot_area` (ha).

It is also used to convert GWFlow basin water-balance volumes to watershed-average depth in [`gwflow_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L870-L889):

$$d = \frac{V}{A_{\text{tot}} \times 10000} \times 1000$$

where $d$ is depth (mm), $V$ is volume ($\text{m}^3$), and $A_{\text{tot}}$ is `tot_area` (ha).
