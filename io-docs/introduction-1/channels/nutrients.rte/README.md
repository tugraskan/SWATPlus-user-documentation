---
description: "The nutrients.rte file defines reach-scale nutrient and water-quality reduction parameters used by the SWAT+ routing and water-quality calculations, including denitrification rate coefficients, turbidity and suspended-solids reduction relationships, phosphorus reduction coefficients, and minimum concentration thresholds for key constituents."
---

# nutrients.rte

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The nutrients.rte file defines reach-scale nutrient and water-quality reduction parameters used by the SWAT+ routing and water-quality calculations, including denitrification rate coefficients, turbidity and suspended-solids reduction relationships, phosphorus reduction coefficients, and minimum concentration thresholds for key constituents.

SWAT+ uses the literal filename `nutrients.rte` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [rte_read_nut.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/rte_read_nut.f90#L29). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying the reach or drainage feature associated with these nutrient parameters | string | n/a | — | — |
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
