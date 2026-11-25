---
description: >-
  This file contains pointers referencing several files that specify the
  reservoir and wetland initialization parameters.
---

# initial.res

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the reservoir and wetland initialization record | string |  |  |  |
| [org\_min](res_org_min.md) | Pointer to the organic-mineral initialization file | string |  |  |  |
| [pest](res_pest.md) | Pointer to the pesticide initialization file | string |  |  |  |
| [path](path.md) | Pointer to the pathogen initialization file for reservoirs | string |  |  |  |
| [hmet](hmet.md) | Pointer to the heavy metals initialization file (not used) | string |  |  |  |
| [salt](res_salt.md) | Intended salt-initialization pointer (read but not used here in main 6f515368; active initialization uses reservoir.res\_cs) | string |  |  |  |

{% hint style="warning" %}
In SWAT+ main (6f515368), the `path` field initializes pathogens for reservoirs. In [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L68-L69), the code resolves a `path` value for wetlands but does not apply the resulting wetland initialization index. The `hmet` field is not used.
{% endhint %}
