---
description: "This file supplies channel nutrient and water-quality reduction parameters."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies channel nutrient and water-quality reduction parameters.

SWAT+ looks for `nutrients.rte` in the simulation working directory; it is not selected through `file.cio`. [`proc_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_hru.f90#L72) calls [`rte_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rte_read_nut.f90#L24-L57) to parse rows into `rte_nut`.

{% hint style="warning" %}
In SWAT+ main (`6f515368`), `rte_nut` has no downstream executable references (`reads=none`). Based on source reading, supplying `nutrients.rte` does not alter channel or overland nutrient routing.
{% endhint %}

# nutrients.rte

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | Drainage_Ditch | — |
| [len_inc](len_inc.md) | Segment length over which nutrient and quality reductions are applied | real | m | 250 | — |
| [no3_slp](no3_slp.md) | Slope of the denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | (mgN/m2/h)/ppm | 0.86 | — |
| [no3_int](no3_int.md) | Intercept of the denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | mgN/m2/h | 0.17 | — |
| [no3_slp_ob](no3_slp_ob.md) | Slope of the overland-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | (mgN/m2/h)/ppm | 0.48 | — |
| [no3_int_ob](no3_int_ob.md) | Intercept of the overland-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | mgN/m2/h | 1.30 | — |
| [no3_slp_ub](no3_slp_ub.md) | Slope of the tile-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | (mgN/m2/h)/ppm | 1.50 | — |
| [no3_int_ub](no3_int_ub.md) | Intercept of the tile-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | mgN/m2/h | 0.03 | — |
| [turb_slp](turb_slp.md) | Slope of the turbidity reduction equation relating inflow turbidity to turbidity reduction | real | del ppm/ppm | -0.0002 | — |
| [turb_int](turb_int.md) | Intercept of the turbidity reduction equation relating inflow turbidity to turbidity reduction | real | ppm | 0.175 | — |
| [tss_slp](tss_slp.md) | Slope of the total suspended solids (TSS) reduction equation relating inflow turbidity to TSS reduction | real | del ppm/ppm | 0.457 | — |
| [tss_int](tss_int.md) | Intercept of the total suspended solids (TSS) reduction equation relating inflow turbidity to TSS reduction | real | ppm | 0.534 | — |
| [tp_slp](tp_slp.md) | Slope of the total phosphorus reduction equation relating turbidity reduction to total phosphorus reduction | real | del ppm/ppm | 0.375 | — |
| [tp_int](tp_int.md) | Intercept of the total phosphorus reduction equation relating turbidity reduction to total phosphorus reduction | real | ppm | 1.312 | — |
| [srp_slp](srp_slp.md) | Slope of the soluble reactive phosphorus reduction equation relating total phosphorus reduction to soluble reactive phosphorus reduction | real | del ppm/ppm | 0.646 | — |
| [srp_int](srp_int.md) | Intercept of the soluble reactive phosphorus reduction equation relating total phosphorus reduction to soluble reactive phosphorus reduction | real | ppm | 0.207 | — |
| [turb_tss_slp](turb_tss_slp.md) | Slope relating turbidity to total suspended solids concentrations | real | ppm | 0.35 | 0.2-0.4 |
| [no3_min_conc](no3_min_conc.md) | Minimum nitrate concentration retained in reach outflow | real | ppm | 0.05 | — |
| [tp_min_conc](tp_min_conc.md) | Minimum total phosphorus concentration retained in reach outflow | real | ppm | 0.06 | — |
| [tss_min_conc](tss_min_conc.md) | Minimum total suspended solids concentration retained in reach outflow | real | ppm | 5 | — |
| [srp_min_conc](srp_min_conc.md) | Minimum soluble reactive phosphorus concentration retained in reach outflow | real | ppm | 0.015 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
