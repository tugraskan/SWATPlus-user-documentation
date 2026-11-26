---
description: "This file supplies channel sediment, nutrient settling, and erosion parameters."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies channel sediment, nutrient settling, and erosion parameters.

SWAT+ looks for `sed_nut.cha` in the simulation working directory; it is not selected through `file.cio`. See the [`sd_hydsed_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_read.f90#L75) reader. Records are matched by comparing `sd_chd1%name` against the channel's `cha_hyd` name in [`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L284-L289).

# sed_nut.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [order](order.md) | Order label stored with this channel parameter record (unused in simulation) | string | n/a | — | — |
| [pk_rto](pk_rto.md) | Ratio of peak to mean daily flow in the channel | real | ratio | 1.0 | — |
| [fp_inun_days](fp_inun_days.md) | Number of days the flood plain remains inundated after a flood event (no effect on SWAT+ dev; see the field page) | real | days | 5.0 | — |
| [n_setl](n_setl.md) | Ratio of nitrogen settling to overall sediment settling for the channel reach (unused in simulation) | real | ratio | 0.5 | — |
| [p_setl](p_setl.md) | Ratio of phosphorus settling to overall sediment settling for the channel reach (unused in simulation) | real | ratio | 0.5 | — |
| [n_sol_part](n_sol_part.md) | Instream transformation coefficient converting soluble nitrogen to particulate nitrogen | real | none | 0.01 | — |
| [p_sol_part](p_sol_part.md) | Instream transformation coefficient converting soluble phosphorus to particulate phosphorus | real | none | 0.01 | — |
| [n_dep_enr](n_dep_enr.md) | Enrichment factor for nitrogen in deposition | real | none | 0.5 | — |
| [p_dep_enr](p_dep_enr.md) | Enrichment factor for phosphorus in deposition | real | none | 0.5 | — |
| [arc_len_fr](arc_len_fr.md) | Fraction of the channel arc length over which bank erosion is permitted to occur (unused in bank erosion at 6f515368) | real | fraction | 1.2 | — |
| [bed_exp](bed_exp.md) | Exponential coefficient controlling bed erosion rate for the channel reach (used on SWAT+ dev; overwritten to 1.0 on main) | real | none | 1.5 | — |
| [wash_bed_fr](wash_bed_fr.md) | Intended washload fraction; actually multiplies bank-erosion channel deposition and bed erosion | real | fraction | 0.1 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
