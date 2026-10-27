---
description: >-
  This file contains pointers referencing several files that specify the
  reservoir and wetland initialization parameters.
---

# initial.res

| Field                       | Description                                             | Type   |
| --------------------------- | ------------------------------------------------------- | ------ |
| [name](name.md)​ | Name of the reservoir and wetland initialization record | string |
| [org\_min](res_org_min.md)​ | Pointer to the organic-mineral initialization file      | string |
| [pest](res_pest.md)​        | Pointer to the pesticide initialization file            | string |
| path​ | Pointer to the pathogen initialization file for reservoirs | string |
| hmet​                       | Currently not used                                      | string |
| [salt](res_salt.md)​ | Currently not used in initial.res in SWAT+ main (6f515368) | string |

{% hint style="warning" %}
In SWAT+ main (6f515368), the path field initializes pathogens for reservoirs. The code resolves a path value for wetlands but does not apply the resulting wetland initialization index. The hmet field is not used.
{% endhint %}
