---
description: Dry weight of biomass removed by grazing daily
---

# bm\_eat

**Code reference:** `grazeop_db(igrazop)%eat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L126), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

Dry weight of above-ground plant biomass removed daily by grazing (`(kg/ha)/day`; default `0.0`, valid range `0.0–500.0`).

In [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L47-L56) and [`#L74-L75`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L74-L75), SWAT+ computes the daily grazed fraction of community above-ground biomass, removes that fraction from each plant's seed, leaf, stem, above-ground, and total biomass pools, and reduces leaf area index and accumulated heat-unit fraction:

$$f_{\text{eat}} = \min\!\left(\frac{B_{\text{eat}}}{B_{\text{abg}}},\, 1\right)$$

where $f_{\text{eat}}$ is the daily grazed fraction of community above-ground biomass (dimensionless), $B_{\text{eat}}$ is `bm_eat` (`(kg/ha)/day`), and $B_{\text{abg}}$ is total community above-ground biomass (`pl_mass(j)%ab_gr_com%m`, `kg/ha`).

$$\text{LAI} \leftarrow \text{LAI} - \frac{B_{\text{eat}}}{1000}, \qquad \text{PHU}_{\text{acc}} \leftarrow \text{PHU}_{\text{acc}}\left(1 - \frac{B_{\text{eat}}}{1000}\right)$$

where $\text{LAI}$ is the leaf area index (dimensionless), $\text{PHU}_{\text{acc}}$ is the accumulated heat-unit fraction (dimensionless), and $B_{\text{eat}}$ is `bm_eat` (`(kg/ha)/day`).
