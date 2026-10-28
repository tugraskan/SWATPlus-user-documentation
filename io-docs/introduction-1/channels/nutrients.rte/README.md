---
description: "This file supplies channel nutrient and water-quality reduction parameters."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies channel nutrient and water-quality reduction parameters.

SWAT+ looks for `nutrients.rte` in the simulation working directory; it is not selected through `file.cio`. See the [rte_read_nut.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/rte_read_nut.f90#L29) reader.

# nutrients.rte

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [len_inc](len_inc.md) | Segment length over which nutrient and quality reductions are applied | real | — | — | — |
| [no3_slp](no3_slp.md) | Slope of the denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | — | — | — |
| [no3_int](no3_int.md) | Intercept of the denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | — | — | — |
| [no3_slp_ob](no3_slp_ob.md) | Slope of the overland-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | — | — | — |
| [no3_int_ob](no3_int_ob.md) | Intercept of the overland-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | — | — | — |
| [no3_slp_ub](no3_slp_ub.md) | Slope of the tile-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | — | — | — |
| [no3_int_ub](no3_int_ub.md) | Intercept of the tile-flow denitrification rate equation relating inflow nitrate concentration to areal denitrification rate | real | — | — | — |
| [turb_slp](turb_slp.md) | Slope of the turbidity reduction equation relating inflow turbidity to turbidity reduction | real | — | — | — |
| [turb_int](turb_int.md) | Intercept of the turbidity reduction equation relating inflow turbidity to turbidity reduction | real | — | — | — |
| [tss_slp](tss_slp.md) | Slope of the total suspended solids (TSS) reduction equation relating inflow turbidity to TSS reduction | real | — | — | — |
| [tss_int](tss_int.md) | Intercept of the total suspended solids (TSS) reduction equation relating inflow turbidity to TSS reduction | real | — | — | — |
| [tp_slp](tp_slp.md) | Slope of the total phosphorus reduction equation relating turbidity reduction to total phosphorus reduction | real | — | — | — |
| [tp_int](tp_int.md) | Intercept of the total phosphorus reduction equation relating turbidity reduction to total phosphorus reduction | real | — | — | — |
| [srp_slp](srp_slp.md) | Slope of the soluble reactive phosphorus reduction equation relating total phosphorus reduction to soluble reactive phosphorus reduction | real | — | — | — |
| [srp_int](srp_int.md) | Intercept of the soluble reactive phosphorus reduction equation relating total phosphorus reduction to soluble reactive phosphorus reduction | real | — | — | — |
| [turb_tss_slp](turb_tss_slp.md) | Slope relating turbidity to total suspended solids concentrations | real | — | — | — |
| [no3_min_conc](no3_min_conc.md) | Minimum nitrate concentration retained in reach outflow | real | — | — | — |
| [tp_min_conc](tp_min_conc.md) | Minimum total phosphorus concentration retained in reach outflow | real | — | — | — |
| [tss_min_conc](tss_min_conc.md) | Minimum total suspended solids concentration retained in reach outflow | real | — | — | — |
| [srp_min_conc](srp_min_conc.md) | Minimum soluble reactive phosphorus concentration retained in reach outflow | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
