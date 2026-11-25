---
description: Optimal temperature for plant growth
---

# tmp\_opt

**Code reference:** `pldb(ic)%t_opt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L53)).

**Current use:** the temperature stress factor (1 = no stress) is the sine form below, limited to 0–1 ([`pl_tstr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_tstr.f90#L68-L77)). It replaces the older SWAT exponential form computed just before it.

$$f = \sin\left(1.5707\,\frac{T - T_{b}}{T_{o} - T_{b}}\right)$$

where $f$ is the temperature stress factor (dimensionless; `1` = no stress), $T$ is the daily mean air temperature (`°C`), $T_{b}$ is [tmp\_base](tmp_base.md) (`°C`), and $T_{o}$ is `tmp_opt` (`°C`).

Both optimal and base temperatures are very stable for cultivars within a species.

Optimal temperature for plant growth is difficult to measure directly. Looking at the figure below, one might be tempted to select the temperature corresponding to the peak of the plot as the optimal temperature. This would not be correct. The peak of the plot defines the optimal temperature for leaf development—not for plant growth.

<img src="../../../.gitbook/assets/image (13).png" alt="" data-size="original">

If an optimal temperature cannot be obtained through a review of literature, use the optimal temperature listed for a plant already in the database with similar growth habits.

Review of temperatures for many different plants have provided generic values for base and optimal temperatures as a function of growing season. In situations, where temperature information is unavailable, these values may be used. For warm season plants, the generic base temperature is \~8ºC and the generic optimal temperature is \~25ºC. For cool season plants, the generic base temperature is \~0ºC and the generic optimal temperature is \~13ºC.
