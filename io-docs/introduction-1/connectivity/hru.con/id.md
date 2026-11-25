---
description: Unique ID of the object
---

# id

**Code reference:** `ob(i)%num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L353)).

The unique ID of the object is a primary key that is referenced by [obj\_id](obj_id.md).

{% hint style="warning" %}
Please be aware that the unique ID of the object is not necessarily the same as the ID in QSWAT+. The GIS interface numbers the objects when they are first created. Later in the process, some objects might be replaced by others, e.g. channels that are located within reservoirs. When the SWAT+ Editor writes the SWAT+ input files, it assigns consecutive ID numbers to those objects that are still included in the final setup of the model. It is extremely important to pay attention to this when identifying the channels that streamflow gauges are located on for comparing simulated and observed data.
{% endhint %}

SWAT+ [locates a receiving object by its row position](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L221-L276), not by searching for this ID. Number the records 1, 2, 3, ... in row order in each connect file.
