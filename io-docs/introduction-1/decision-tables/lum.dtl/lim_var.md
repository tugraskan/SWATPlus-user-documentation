---
description: Limit variable
---

# lim\_var

**Code reference:** `dtbl_lum(i)%cond(ic)%lim_var` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/conditional_module.f90#L11)).

The condition variables, for which a limit variable must be specified, are listed in the table below. Some limit variables must be used in combination with a limit operator (see [lim\_op](lim_op.md)).&#x20;

<table><thead><tr><th width="191">Condition variable</th><th>Limit variable</th><th>Description</th><th>Limit operator?</th></tr></thead><tbody><tr><td>soil_water</td><td>wp</td><td>Wilting point</td><td>yes</td></tr><tr><td>soil_water</td><td>fc</td><td>Field capacity</td><td>yes</td></tr><tr><td>soil_water</td><td>ul</td><td>Upper limit</td><td>yes</td></tr><tr><td>plant_gro</td><td>y</td><td>Plant growing</td><td>no</td></tr><tr><td>plant_name_gro</td><td></td><td></td><td>no</td></tr><tr><td>hyd_soil_group</td><td></td><td></td><td>no</td></tr><tr><td>land_use</td><td></td><td></td><td>no</td></tr><tr><td>tillage</td><td></td><td></td><td>no</td></tr><tr><td>plant</td><td></td><td></td><td>no</td></tr><tr><td>ch_use</td><td></td><td></td><td>no</td></tr><tr><td>vol</td><td>evol</td><td>Emergency volume</td><td>yes</td></tr><tr><td>vol</td><td>pvol</td><td>Principal volume</td><td>yes</td></tr><tr><td>vol</td><td>e-pv</td><td>Emergency minus principal volume</td><td>no</td></tr><tr><td>wet_depth</td><td></td><td></td><td>no</td></tr><tr><td>vol_wet</td><td>evol</td><td>Emergency volume</td><td>yes</td></tr><tr><td>vol_wet</td><td>pvol</td><td>Principal volume</td><td>yes</td></tr></tbody></table>
