---
description: Lateral flow travel time
---

# lat\_ttime

**Code reference:** `hyd_db(ithyd)%lat_ttime`

**Declared type:** `hydrology_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrol_read.f90#L47), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L8)).

{% hint style="info" %}
Setting lat_ttime to 0.0 allows SWAT+ to calculate the lateral-flow travel time from soil hydraulic properties. Enter a specific value only when the lateral-flow travel time is known.
{% endhint %}
