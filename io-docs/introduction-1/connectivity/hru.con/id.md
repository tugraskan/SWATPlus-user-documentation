---
description: Unique ID of the object
---

# id

**Code reference:** `ob(i)%num`

**Declared type:** `object_connectivity` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hyd_read_connect.f90#L298), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L350)).

The unique ID of the object is a primary key that is referenced by [obj\_id](obj_id.md).

{% hint style="warning" %}
Please be aware that the unique ID of the object is not necessarily the same as the ID in QSWAT+. The GIS interface numbers the objects when they are first created. Later in the process, some objects might be replaced by others, e.g. channels that are located within reservoirs. When the SWAT+ Editor writes the SWAT+ input files, it assigns consecutive ID numbers to those objects that are still included in the final setup of the model. It is extremely important to pay attention to this when identifying the channels that streamflow gauges are located on for comparing simulated and observed data.
{% endhint %}
