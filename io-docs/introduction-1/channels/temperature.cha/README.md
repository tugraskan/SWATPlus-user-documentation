---
description: "This file supplies coefficients, lag times, and shade settings for channel water temperature."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies coefficients, lag times, and shade settings for channel water temperature.

# temperature.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
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
| [sf_on](sf_on.md) | Activation flag for the shade factor file | integer | n/a | — | — |
| [ssff](ssff.md) | Default shade factor value used when the shade factor file is not active | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
