---
description: This file contains the physical soil properties.
---

# soils.sol

The structure of the file **soils.sol** is different than that of most other SWAT+ input files. Each soil entry consists of one profile line specifying variables that apply to the entire soil profile (see first table below), followed by [`nly`](nly.md) layer-specific lines (see second table below), dynamically allocated when read by [`soil_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_db_read.f90#L58-L71). When `soil_lyr_depths.sol` is not present and the first input layer depth exceeds 19.5 mm, SWAT+ automatically inserts a 10 mm surface layer during initialization ([`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L71-L81)). The figure below illustrates the structure of a **soils.sol** file with three soils. Please note that due to space restrictions not all layer-specific variables are included.

![Example of a soils.sol file with three soils](<../../../.gitbook/assets/image (15).png>)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name-soils.sol.md) | Name of the soil | string | n/a |  |  |
| [nly](nly.md) | Number of layers in the soil | integer | none |  |  |
| [hyd\_grp](hyd_grp.md) | Hydrologic soil group of the soil | string | n/a |  |  |
| [dp\_tot](dp_tot.md) | Maximum rooting depth | real | mm |  |  |
| [anion\_excl](anion_excl.md) | Fraction of porosity (void space) from which anions are excluded | real | fraction |  |  |
| [perc\_crk](perc_crk.md) | Potential or maximum crack volume of the soil profile expressed as a fraction of the total soil volume | real | fraction |  |  |
| [texture](texture.md) | Texture of the soil | string | n/a |  |  |

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dp](dp.md) | Depth from the soil surface to the bottom of the soil layer | real | mm |  |  |
| [bd](bd.md) | Moist bulk density of the soil layer | real | Mg/m**3 |  |  |
| [awc](awc.md) | Available water capacity of the soil layer | real | mm H2O/mm soil |  |  |
| [soil\_k](soil_k.md) | Saturated hydraulic conductivity of the soil layer | real | mm/hr |  |  |
| [carbon](carbon.md) | Organic carbon content of the soil layer | real | % |  |  |
| [clay](clay.md) | Clay content of the soil layer | real | % |  |  |
| [silt](silt.md) | Silt content of the soil layer | real | % |  |  |
| [sand](sand.md) | Sand content of the soil layer | real | % |  |  |
| [rock](rock.md) | Rock fragment content of the soil layer | real | % |  |  |
| [alb](alb.md) | Moist soil albedo of the top layer | real | fraction |  |  |
| [usle\_k](usle_k.md) | USLE equation soil erodibility (K) factor of the top layer | real | none |  |  |
| [ec](ec.md) | Electrical conductivity of the soil layer | real | dS/m |  |  |
| [caco3](caco3.md) | Calcium carbonate (CaCO3) content of the soil layer | real | % |  |  |
| [ph](ph.md) | pH value of the soil layer | real | none |  |  |
