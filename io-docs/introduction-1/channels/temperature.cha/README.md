---
description: "Defines reach-level temperature inputs, including coefficients and lag times that govern how snowmelt, groundwater, surface runoff, and lateral flow contribute to channel water temperature, along with calibration coefficients and shade factor controls."
---

# temperature.cha

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines reach-level temperature inputs, including coefficients and lag times that govern how snowmelt, groundwater, surface runoff, and lateral flow contribute to channel water temperature, along with calibration coefficients and shade factor controls.

The reader obtains the filename through `in_cha%temp`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Reach name identifying the channel reach for which temperature inputs apply | string | n/a | — | — |
| [sno_mlt](sno_mlt.md) | Coefficient influencing the magnitude of snowmelt temperature contributions to the channel | real | — | — | — |
| [gw](gw.md) | Coefficient influencing the magnitude of groundwater temperature contributions to the channel | real | — | — | — |
| [sur_lat](sur_lat.md) | Coefficient influencing the magnitude of surface and lateral flow temperature contributions to the channel | real | — | — | — |
| [sno_lag](sno_lag.md) | Average air temperature lag, in days, applied to snowmelt temperature inputs | real | — | — | — |
| [gw_lag](gw_lag.md) | Average air temperature lag, in days, applied to groundwater temperature inputs | real | — | — | — |
| [surf_lag](surf_lag.md) | Average air temperature lag, in days, applied to surface runoff temperature inputs | real | — | — | — |
| [lat_lag](lat_lag.md) | Average air temperature lag, in days, applied to lateral flow temperature inputs | real | — | — | — |
| [lat_lag_coef](lat_lag_coef.md) | Coefficient applied to the lateral flow air temperature lag | real | — | — | — |
| [surf_lag_coef](surf_lag_coef.md) | Coefficient applied to the surface runoff air temperature lag; also applied to snow temperature lag | real | — | — | — |
| [gw_lag_coef](gw_lag_coef.md) | Coefficient applied to the groundwater air temperature lag | real | — | — | — |
| [hex_coef1](hex_coef1.md) | Coefficient used to calibrate the dew point temperature contribution | real | — | — | — |
| [hex_coef2](hex_coef2.md) | Coefficient used to calibrate channel geometry relationships | real | — | — | — |
| [sf_on](sf_on.md) | Activation flag for the shade factor file; 1 indicates the file is used, 0 indicates the value is taken from the calibration file | integer | n/a | — | — |
| [ssff](ssff.md) | Default shade factor value used when the shade factor file is not active | real | — | — | — |
