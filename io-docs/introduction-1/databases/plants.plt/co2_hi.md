---
description: >-
  Elevated CO2 atmospheric concentration corresponding the 2nd point on the
  radiation use efficiency curve
---

# co2\_hi

**Code reference:** `pldb(ic)%co2hi`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L75)).

The 1st point on the radiation use efficiency curve is comprised of the ambient CO2 concentration, 330 μL CO2/L air, and the biomass-energy ratio reported for [bm\_e](untitled-17.md).

In order to assess the impact of climate change on agricultural productivity, SWAT+ incorporates equations that adjust RUE for elevated atmospheric CO2 concentrations. Values must be entered for _co2\_hi_ and [bm\_e\_hi](bm_e_hi.md) in the plant database whether or not the user plans to simulate climate change.

{% hint style="info" %}
For simulations in which elevated CO2 levels are not modeled, _co2\_hi_ should be set to some number greater than 330 ppmv and [bm\_e\_hi](bm_e_hi.md) should be set to some number greater than [bm\_e](untitled-17.md).
{% endhint %}

To obtain radiation-use efficiency values at elevated CO2 levels for plant species not currently in the database, plants should be established in growth chambers set up in the field or laboratory where CO2 levels can be controlled. RUE values are determined using the same methodology described in the explanation of [bm\_e](untitled-17.md).
