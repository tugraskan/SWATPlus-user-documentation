---
description: "Defines the number of carbon soil layers used by the carbon module, read as a single record containing an integer count of layers."
---

# carbon_layers.prt

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines the number of carbon soil layers used by the carbon module, read as a single record containing an integer count of layers.

SWAT+ uses the literal filename `carbon_layers.prt` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [carbon_layers_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/carbon_layers_read.f90#L29). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 37

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [n_lyr](n_lyr.md) | integer count of carbon soil layers to be read for the simulation | integer | n/a | — | — |
