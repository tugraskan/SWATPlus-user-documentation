---
description: Residue cover factor in the USLE C factor equation
---

# ero\_rsdfac

**Code reference:** `pldb(ic)%ero_rsdfac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L95), [default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L30)).

Column 52. Weight of above-ground residue in the daily USLE C factor (default 0.75; values ≤ 0 are replaced by 0.75). [`ero_cfactor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_cfactor.f90#L54-L71) computes:

$$
C = \max\left(10^{-10},\; e^{-\sum_p 2\,r_p\,(R_p + 1)/1000} \cdot e^{-\sum_p b_p\,B_p/1000}\right)
$$

where:

- $C$ is the USLE C factor (dimensionless),
- $r_p$ is `ero_rsdfac` of plant $p$ in the HRU's community (dimensionless),
- $R_p$ is plant $p$'s above-ground residue (kg/ha),
- $b_p$ is [ero\_biofac](ero_biofac.md) of plant $p$ (dimensionless), and
- $B_p$ is plant $p$'s above-ground biomass (kg/ha).

Each exponential term is limited to between 1e-8 and 1. The overland-flow erosion routine uses the same terms without the factor 2 on residue ([`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L177-L183)).

In SWAT+ main this column held `rsd_pctcov`, which was read but had no effect. A file with the older 54-column layout gets the default 0.75 here.
