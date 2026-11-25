---
description: "POD number that links this POD entry to point_of_diver.wro"
---

# num (POD)

**Code reference:** `pou(ipou)%pod(ipod)%num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L16), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L95-L98)).

The POD number, as given in the first column of [point_of_diver.wro](../point_of_diver.wro/README.md) (default: `0`). After both files are read, SWAT+ matches each POD listed in `point_of_diver.wro` against this column of every POU that POD serves, to find the POD's position in the POU's list ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L257-L268)). That position decides which POD duty, fraction and limits a withdrawal uses, and which POD row it is reported on.

{% hint style="warning" %}
If a POU named in `point_of_diver.wro` has no POD entry with this number, the position stays 0 and the withdrawal indexes an entry that does not exist. Make every POU–POD pair appear in both files with the same POD number.
{% endhint %}

In SWAT+ main this column was overwritten by position 5 and the position came from a `pod_num` column in `point_of_diver.wro`; dev removed that column.
