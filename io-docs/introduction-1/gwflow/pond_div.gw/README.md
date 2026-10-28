---
description: "Provides a daily time-series of specified diversion volumes for each groundwater pond, with one record per date containing a diversion value for every pond."
---

# pond_div.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Provides a daily time-series of specified diversion volumes for each groundwater pond, with one record per date containing a diversion value for every pond.

SWAT+ uses the literal filename `pond_div.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2017). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Initialization skips metadata and column-header records and leaves the file open. The pond routine reads year, month, day, then one diversion value for each of gw_npond ponds. The date columns and diversion values belong to one repeated time-series record.

### Pond diversion series

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [year](year.md) | Calendar year of the diversion time-series date | integer | n/a | — | — |
| [month](month.md) | Calendar month of the diversion time-series date | integer | n/a | — | — |
| [day](day.md) | Calendar day of the diversion time-series date | integer | n/a | — | — |
| [div](div.md) | Specified diversion volume applied to each pond on the given date, as declared in gw_pond_info(r)%div | real | — | — | — |
