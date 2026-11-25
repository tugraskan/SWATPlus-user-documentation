---
description: Object ID in QSWAT+
---

# gis\_id

**Code reference:** `ob(i)%gis_id` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L355)).

{% hint style="warning" %}
Please be aware that the ID in QSWAT+ is not necessarily the same as the unique ID of the object. The GIS interface numbers the objects when they are first created. Later in the process, some objects might be replaced by others, e.g. channels that are located within reservoirs. When the SWAT+ Editor writes the SWAT+ input files, it assigns consecutive ID numbers to those objects that are still included in the final setup of the model. It is extremely important to pay attention to this when identifying the channels that streamflow gauges are located on for comparing simulated and observed data.
{% endhint %}
