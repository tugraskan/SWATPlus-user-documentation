---
description: Effective hydraulic conductivity of the channel alluvium
---

# k

**Code reference:** `sd_chd(idb)%chk`

**Declared type:** `swatdeg_hydsed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L61), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L26)).

The table below lists typical values for k for various alluvium materials (Lane, 1983). For perennial streams with continuous groundwater contribution, the effective conductivity will be zero.

<table><thead><tr><th valign="top">Bed material group</th><th width="270" valign="top">Bed material characteristics</th><th valign="top">Hydraulic conductivity</th></tr></thead><tbody><tr><td valign="top">1 - Very high loss rate</td><td valign="top">Very clean gravel and large sand</td><td valign="top"><p> </p><p>> 127 mm/hr</p></td></tr><tr><td valign="top">2 - High loss rate</td><td valign="top">Clean sand and gravel, field conditions</td><td valign="top"><p> </p><p>51-127 mm/hr</p></td></tr><tr><td valign="top">3 - Moderately high loss rate</td><td valign="top">Sand and gravel mixture with low silt-clay content</td><td valign="top"><p> </p><p>25-76 mm/hr</p></td></tr><tr><td valign="top">4 - Moderate loss rate</td><td valign="top">Sand and gravel mixture with high silt-clay content</td><td valign="top"><p> </p><p>6-25 mm/hr</p></td></tr><tr><td valign="top">5 - Insignificant to low loss rate</td><td valign="top">Consolidated bed material; high silt-clay content</td><td valign="top"><p> </p><p>0.025-2.5 mm/hr</p></td></tr></tbody></table>

#### References

> Lane (1983)
