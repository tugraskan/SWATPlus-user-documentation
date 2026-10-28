---
description: "This file supplies channel sediment, nutrient settling, and erosion parameters."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies channel sediment, nutrient settling, and erosion parameters.

SWAT+ looks for `sed_nut.cha` in the simulation working directory; it is not selected through `file.cio`. See the [sd_hydsed_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L74) reader.

# sed_nut.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [order](order.md) | Order label stored with this channel parameter record | string | n/a | — | — |
| [pk_rto](pk_rto.md) | Ratio of peak to mean daily flow in the channel | real | — | — | — |
| [fp_inun_days](fp_inun_days.md) | Number of days the flood plain remains inundated after a flood event | real | — | — | — |
| [n_setl](n_setl.md) | Ratio of nitrogen settling to overall sediment settling for the channel reach | real | — | — | — |
| [p_setl](p_setl.md) | Ratio of phosphorus settling to overall sediment settling for the channel reach | real | — | — | — |
| [n_sol_part](n_sol_part.md) | Instream transformation coefficient converting soluble nitrogen to particulate nitrogen | real | — | — | — |
| [p_sol_part](p_sol_part.md) | Instream transformation coefficient converting soluble phosphorus to particulate phosphorus | real | — | — | — |
| [n_dep_enr](n_dep_enr.md) | Enrichment factor for nitrogen in the remaining water after deposition | real | — | — | — |
| [p_dep_enr](p_dep_enr.md) | Enrichment factor for phosphorus in the remaining water after deposition | real | — | — | — |
| [arc_len_fr](arc_len_fr.md) | Fraction of the channel arc length over which bank erosion is permitted to occur | real | — | — | — |
| [bed_exp](bed_exp.md) | Exponential coefficient controlling bed erosion rate for the channel reach | real | — | — | — |
| [wash_bed_fr](wash_bed_fr.md) | Fraction of bank erosion material that is transported as washload rather than bedload | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
