---
description: >-
  This file references several other files, which initialize nutrients and
  constituents in channels.
---

# initial.cha

| Field                     | Description                                        |  Type  |
| ------------------------- | -------------------------------------------------- | :----: |
| [name](name.md)           | Name of the channel initialization record          | string |
| [org\_min](ch_org_min.md) | Pointer to the organic-mineral initialization file | string |
| [pest](ch_pest.md)        | Pointer to the pesticide initialization file       | string |
| path                      | Currently not used                                 | string |
| hmet                      | Currently not used                                 | string |
| [salt](ch_salt.md) | Currently not used in initial.cha in SWAT+ main (6f515368) | string |

{% hint style="warning" %}
There are no plans to work on the pathogen and heavy metal routines in the foreseeable future unless there is a demand for it in the user community.
{% endhint %}
