---
description: "Links HRUs to groundwater cells. Each association supplies an HRU identifier, total HRU area, groundwater cell identifier, and intersection area used to compute area fractions."
---

# hrucell.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Links HRUs to groundwater cells. Each association supplies an HRU identifier, total HRU area, groundwater cell identifier, and intersection area used to compute area fractions.

SWAT+ uses the literal filename `hrucell.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2128). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [hru_id](hru_id.md) | integer identifier of the HRU to which this groundwater cell belongs, used to index HRU-level groundwater arrays | integer | n/a | — | — |
| [hru_area](hru_area.md) | total area of the HRU, used as the denominator when computing the fractional area contribution of each groundwater cell within the HRU | real | — | — | — |
| [hru_cells](hru_cells.md) | Groundwater cell identifier for this HRU-cell association | integer | n/a | — | — |
| [poly_area](poly_area.md) | Area of the HRU-cell intersection used to calculate HRU and cell area fractions | real | — | — | — |
