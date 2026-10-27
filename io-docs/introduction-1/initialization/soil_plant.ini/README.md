---
description: >-
  This file references several other files, which initialize nutrients and
  constituents in soils.
---

# soil\_plant.ini

| Field                          | Description                                            | Type   |
| ------------------------------ | ------------------------------------------------------ | ------ |
| [name](name-soil_plant.ini.md) | Name of the soil and plant initialization              | string |
| [sw\_frac](sw_frac.md) | Not used. Initial soil water is controlled by sw_init in parameters.bsn. | real |
| [nutrients](nutrients.md)      | Pointer to the nutrient initialization file            | string |
| [pest](pest.md)                | Pointer to the pesticide initialization file           | string |
| path | Name of a record in path_hru.ini that initializes pathogen concentrations in soil and plants. | string |
| [salt](salt.md)                | Pointer to the salt initialization file                | string |
| hmet | Name of a record in hmet_hru.ini that initializes heavy-metal concentrations in soil and plants. | string |
| [cs](cs.md)                    | Pointer to the constituent soil initialization in cs\_hru.ini; this column is read only when event in codes.bsn is not 0 | string |

{% hint style="warning" %}
There are no plans to work on the pathogen and heavy metal routines in the foreseeable future unless there is a demand for it in the user community.
{% endhint %}
