---
description: Minimum LAI during dormant period
---

# lai\_min

**Code reference:** `pldb(ic)%alai_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L75)).

**Current use:** the floor that leaf area falls to during perennial leaf drop ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L44-L53)).

This variable pertains to perennials and trees only. It is not used for other types of plants.

Please see the explanation given for parameter [lai\_pot](untitled-15.md) to obtain additional information about this parameter and methods used to measure it.
