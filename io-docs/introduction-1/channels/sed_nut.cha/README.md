---
description: "Defines per-channel sediment and nutrient parameters used by the hydrosediment (sd) and channel modules, including peak-flow ratios, flood-plain inundation duration, nitrogen and phosphorus settling and transformation ratios, bank and bed erosion fractions, and washload partitioning. Records are read by sd_hydsed_read.f90 and copied into the active channel state during initialization."
---

# sed_nut.cha

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines per-channel sediment and nutrient parameters used by the hydrosediment (sd) and channel modules, including peak-flow ratios, flood-plain inundation duration, nitrogen and phosphorus settling and transformation ratios, bank and bed erosion fractions, and washload partitioning. Records are read by sd_hydsed_read.f90 and copied into the active channel state during initialization.

SWAT+ uses the literal filename `sed_nut.cha` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [sd_hydsed_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L74). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier linking this record to a channel name defined elsewhere in the channel data set | string | n/a | — | — |
| [order](order.md) | Character order label stored with this channel parameter record | string | n/a | — | — |
| [pk_rto](pk_rto.md) | Ratio of peak to mean daily flow in the channel, used to characterize flow variability for sediment transport | real | — | — | — |
| [fp_inun_days](fp_inun_days.md) | Number of days the flood plain remains inundated after a flood event | real | — | — | — |
| [n_setl](n_setl.md) | Ratio of nitrogen settling to overall sediment settling for the channel reach | real | — | — | — |
| [p_setl](p_setl.md) | Ratio of phosphorus settling to overall sediment settling for the channel reach | real | — | — | — |
| [n_sol_part](n_sol_part.md) | Instream transformation coefficient converting soluble nitrogen to particulate nitrogen | real | — | — | — |
| [p_sol_part](p_sol_part.md) | Instream transformation coefficient converting soluble phosphorus to particulate phosphorus | real | — | — | — |
| [n_dep_enr](n_dep_enr.md) | Enrichment factor for nitrogen in the remaining water after deposition, where deposition equals the reciprocal of the enrichment ratio | real | — | — | — |
| [p_dep_enr](p_dep_enr.md) | Enrichment factor for phosphorus in the remaining water after deposition, where deposition equals the reciprocal of the enrichment ratio | real | — | — | — |
| [arc_len_fr](arc_len_fr.md) | Fraction of the channel arc length over which bank erosion is permitted to occur | real | — | — | — |
| [bed_exp](bed_exp.md) | Exponential coefficient controlling bed erosion rate for the channel reach | real | — | — | — |
| [wash_bed_fr](wash_bed_fr.md) | Fraction of bank erosion material that is transported as washload rather than bedload | real | — | — | — |
