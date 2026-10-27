---
description: This file contains the physical soil properties.
---

# soils.sol

The structure of the file **soils.sol** is different than that of most other SWAT+ input files. Depending on the number of soil layers, the file contains two to ten lines per soil. The first line for each soil specifies the variables that apply to the entire soil profile (see first table below). The remaining soil variables are layer-specific and are specified in one line per layer starting one line below the general soil variables (see second table below). The figure below illustrates the structure of a **soils.sol** file with three soils. Please note that due to space restrictions not all layer-specific variables are included.

![Example of a soils.sol file with three soils](<../../../.gitbook/assets/image (15).png>)

| Field                        | Description                                                                                            | Type    | Unit     | Default | Range |
| ---------------------------- | ------------------------------------------------------------------------------------------------------ | ------- | -------- | ------- | ----- |
| [name](name-soils.sol.md)\* | Name of the soil                                                                                       | string  | n/a      |         |       |
| nly                          | Number of layers in the soil                                                                           | integer | none     |         |       |
| [hyd\_grp](hyd_grp.md)\* | Hydrologic soil group of the soil                                                                      | string  | n/a      |         |       |
| [dp\_tot](dp_tot.md)\* | Maximum rooting depth                                                                                  | real    | mm       |         |       |
| [anion\_excl](anion_excl.md) | Fraction of porosity (void space) from which anions are excluded                                       | real    | fraction |         |       |
| [perc\_crk](perc_crk.md)\* | Potential or maximum crack volume of the soil profile expressed as a fraction of the total soil volume | real    |          |         |       |
| [texture](texture.md)        | Texture of the soil                                                                                    | string  | n/a      |         |       |

\* Input-file labels marked with an asterisk have different Fortran names: `name` → `soildb(isol)%s%snam`; `hyd_grp` → `soildb(isol)%s%hydgrp`; `dp_tot` → `soildb(isol)%s%zmx`; `perc_crk` → `soildb(isol)%s%crk`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_db_read.f90#L65).

| Field                | Description                                                 | Type | Unit | Default | Range |
| -------------------- | ----------------------------------------------------------- | ---- | ---- | ------- | ----- |
| dp\* | Depth from the soil surface to the bottom of the soil layer | real |      |         |       |
| [bd](bd.md)          | Moist bulk density of the soil layer                        | real |      |         |       |
| [awc](awc.md)        | Available water capacity of the soil layer                  | real |      |         |       |
| [soil\_k](soil_k.md)\* | Saturated hydraulic conductivity of the soil layer          | real |      |         |       |
| [carbon](carbon.md)\* | Organic carbon content of the soil layer                    | real |      |         |       |
| [clay](clay.md)      | Clay content of the soil layer                              | real |      |         |       |
| [silt](silt.md)      | Silt content of the soil layer                              | real |      |         |       |
| [sand](sand.md)      | Sand content of the soil layer                              | real |      |         |       |
| [rock](rock.md)      | Rock fragment content of the soil layer                     | real |      |         |       |
| [alb](alb.md)        | Moist soil albedo of the top layer                          | real |      |         |       |
| [usle\_k](usle_k.md) | USLE equation soil erodibility (K) factor of the top layer  | real |      |         |       |
| [ec](ec.md)          | Electrical conductivity of the soil layer                   | real |      |         |       |
| [caco3](caco3.md)\* | Calcium carbonate (CaCO3) content of the soil layer         | real |      |         |       |
| [ph](ph.md)          | pH value of the soil layer                                  | real |      |         |       |

\* Input-file labels marked with an asterisk have different Fortran names: `dp` → `soildb(isol)%ly(j)%z`; `soil_k` → `soildb(isol)%ly(j)%k`; `carbon` → `soildb(isol)%ly(j)%cbn`; `caco3` → `soildb(isol)%ly(j)%cal`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_db_read.f90#L71).
