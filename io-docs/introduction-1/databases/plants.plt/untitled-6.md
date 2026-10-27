---
description: Optimal temperature for plant growth
---

# tmp\_opt

**Code reference:** `pldb(ic)%t_opt`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L58)).

Both optimal and base temperatures are very stable for cultivars within a species.

Optimal temperature for plant growth is difficult to measure directly. Looking at the figure below, one might be tempted to select the temperature corresponding to the peak of the plot as the optimal temperature. This would not be correct. The peak of the plot defines the optimal temperature for leaf development—not for plant growth.

<img src="../../../.gitbook/assets/image (13).png" alt="" data-size="original">

If an optimal temperature cannot be obtained through a review of literature, use the optimal temperature listed for a plant already in the database with similar growth habits.

Review of temperatures for many different plants have provided generic values for base and optimal temperatures as a function of growing season. In situations, where temperature information is unavailable, these values may be used. For warm season plants, the generic base temperature is \~8ºC and the generic optimal temperature is \~25ºC. For cool season plants, the generic base temperature is \~0ºC and the generic optimal temperature is \~13ºC.
