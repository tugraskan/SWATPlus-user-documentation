---
description: "Defines puddle (soil compaction) operation records that set post-puddling soil hydraulic and constituent conditions, matched to management operations by name and applied to HRUs during scheduled puddling actions."
---

# puddle.ops

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines puddle (soil compaction) operation records that set post-puddling soil hydraulic and constituent conditions, matched to management operations by name and applied to HRUs during scheduled puddling actions.

SWAT+ uses the literal filename `puddle.ops` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [mgt_read_puddle.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_puddle.f90#L23). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying the puddle operation record, matched against management operation option names to apply the record's puddling effects | string | n/a | — | — |
| [wet_hc](wet_hc.md) | Hydraulic conductivity of the upper soil layer after puddling, copied to the HRU when greater than zero | real | — | — | — |
| [sed](sed.md) | Sediment concentration after puddling, scaled by flow to set the HRU's post-puddling sediment load | real | — | — | — |
| [orgn](orgn.md) | Organic nitrogen concentration after puddling | real | — | — | — |
| [sedp](sedp.md) | Organic phosphorus concentration after puddling | real | — | — | — |
| [no3](no3.md) | Nitrate-nitrogen (NO3-N) concentration after puddling | real | — | — | — |
| [solp](solp.md) | Mineral (soluble) phosphorus concentration after puddling | real | — | — | — |
| [nh3](nh3.md) | Ammonia (NH3) concentration after puddling | real | — | — | — |
| [no2](no2.md) | Nitrite (NO2) concentration after puddling | real | — | — | — |
