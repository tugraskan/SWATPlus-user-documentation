---
description: "Provides daily time-series of channel-groundwater interaction depths. The initialization reader skips metadata and column-header records; the simulation routine then reads rows containing two date columns followed by per-zone depth values. The depth-zone count is derived from the channel-cell connections, and the two date columns are read into a dummy variable without being used to match the simulation date."
---

# chan_depth.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Provides daily time-series of channel-groundwater interaction depths. The initialization reader skips metadata and column-header records; the simulation routine then reads rows containing two date columns followed by per-zone depth values. The depth-zone count is derived from the channel-cell connections, and the two date columns are read into a dummy variable without being used to match the simulation date.

SWAT+ uses the literal filename `chan_depth.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_chan_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_chan_read.f90#L89). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

The initialization reader opens the file and skips metadata and column-header records. The simulation routine then reads rows containing two date columns followed by gw_chan_ndpzn depths. Both date values are read into the same dummy variable; this read does not use them to match the simulation date. The depth-zone count is derived from the channel-cell connections.

### Depth time series

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [jday](jday.md) | First date column of a time-series row, read into a dummy integer variable and not used for simulation-date matching | integer | n/a | — | — |
| [year](year.md) | Second date column of a time-series row, read into the same dummy integer variable as the first date column and not used for simulation-date matching | integer | n/a | — | — |
| [depth_by_zone](depth_by_zone.md) | Depth value for each configured depth zone, stored as specified daily channel depths in meters and indexed by the channel-cell depth zone | real | — | — | — |
