---
description: "Defines groundwater property-zone values for aquifer hydraulic conductivity, specific yield, streambed hydraulic conductivity, and streambed thickness. An optional sixth column supplies thermal conductivity."
---

# zones.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groundwater property-zone values for aquifer hydraulic conductivity, specific yield, streambed hydraulic conductivity, and streambed thickness. An optional sixth column supplies thermal conductivity.

SWAT+ uses the literal filename `zones.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L372). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Skip metadata and column-header records and count data rows to EOF. Each row contains a leading label and four hydraulic values; the thermal value in column 6 is optional and may be null. Parameter arrays are filled in row order; the leading label is not used as an index by this loop.

### Zone record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [zone_id](zone_id.md) | Leading label token for the zone record. This parameter-loading loop does not use it to choose the array index | string | n/a | — | — |
| [aquifer_K](aquifer_k.md) | Aquifer hydraulic conductivity for the indexed zone | real | — | — | — |
| [aquifer_Sy](aquifer_sy.md) | Aquifer specific yield for the indexed zone | real | — | — | — |
| [streambed_K](streambed_k.md) | Streambed hydraulic conductivity for the indexed zone | real | — | — | — |
| [streambed_thick](streambed_thick.md) | Streambed thickness for the indexed zone | real | — | — | — |
| [thermal_K](thermal_k.md) | Optional thermal conductivity for the indexed zone | real | — | — | — |
