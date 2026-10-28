---
description: "Defines phreatophyte groundwater transpiration parameters, specifying depth intervals below ground surface and the corresponding transpiration rates used to compute groundwater-derived ET."
---

# phreato.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines phreatophyte groundwater transpiration parameters, specifying depth intervals below ground surface and the corresponding transpiration rates used to compute groundwater-derived ET.

SWAT+ uses the literal filename `phreato.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1416). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_phyt_dep](gw_phyt_dep.md) | Depth below ground surface (m) at which the phreatophyte ET-rate relationship is defined; used together with the next depth value to form an interval for linear interpolation of transpiration rate | real | — | — | — |
| [gw_phyt_rate](gw_phyt_rate.md) | Transpiration rate (m/day) at the corresponding depth below ground surface; linearly interpolated between adjacent depth entries based on water-table depth within the interval | real | — | — | — |
