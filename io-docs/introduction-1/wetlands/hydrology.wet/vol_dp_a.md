---
description: Volume depth coefficient for HRU impoundment
---

# vol\_dp\_a

**Code reference:** `wet_hyddb(ires)%bcoef`

**Declared type:** `wetland_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_hyd.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L91)).

The parameters [vol\_area\_co](vol_area_co.md), vol\_dp\_a and [vol\_dp\_b](vol_dp_b.md) are coefficients that control how strongly the wetland surface area changes as storage volume changes relative to principal storage. They are used for wetland initialization and to update wetland area for each simulation time step.&#x20;

vol\_dp\_a and [vol\_dp\_b](vol_dp_b.md) are used to infer wetland depth from current storage volume. They are not used independently in a physically transparent way but rather interact through the quadratic. If vol\_dp\_a is smaller than [vol\_dp\_b](vol_dp_b.md), the wetland surface area shrinks more strongly when water volume declines. If vol\_dp\_a is larger than [vol\_dp\_b](vol_dp_b.md), the wetland keeps a larger surface area even at lower storage. [vol\_area\_co](vol_area_co.md) is used to convert the wetland depth to wetland area.&#x20;

The final area is clipped between 0.01 and 1.0, so the effect of extreme values of [vol\_area\_co](vol_area_co.md), vol\_dp\_a, and [vol\_dp\_b](vol_dp_b.md) may get hidden by those limits.

The wetland area affects seepage, groundwater exchange, depth/release calculations, and constituent settling.
