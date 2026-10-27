---
description: Limit operator
---

# lim\_op

**Code reference:** `dtbl_lum(i)%cond(ic)%lim_op` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/conditional_module.f90#L12)).

The limit operators available and the limit and condition variables they are used for are listed in the table below.&#x20;

<table><thead><tr><th width="139">Operator</th><th>Description</th><th>Limit variable</th></tr></thead><tbody><tr><td>*</td><td>Multiply limit variable by limit constant</td><td>fc, wp, ul (soil_water) <br>evol, pvol (vol and vol_wet)</td></tr><tr><td>+</td><td>Add limit constant to limit variable</td><td>fc, wp, ul (soil_water) <br>evol, pvol (vol and vol_wet)</td></tr><tr><td>-</td><td>Subtract limit constant from limit variable</td><td>fc, wp, ul (soil_water) <br>evol, pvol (vol and vol_wet)</td></tr><tr><td>/</td><td>Divide limit variable by limit constant</td><td>fc, wp, ul (soil_water) <br>evol, pvol (vol and vol_wet)</td></tr></tbody></table>
