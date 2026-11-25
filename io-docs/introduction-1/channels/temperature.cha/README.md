---
description: "This file supplies coefficients, lag times, and shade settings for channel water temperature."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies coefficients, lag times, and shade settings for channel water temperature.

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L39-L56) reads rows from `temperature.cha` into `w_temp(1:imax)`, whereas [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L189-L200) exclusively reads `w_temp(0)` ([`#L342`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L361), [`#L352-L365`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L371-L384), [`#L398-L406`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L417-L425)). Because `w_temp(0)` keeps the built-in [`water_temperature_data`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L169-L185) defaults (`sf_on = 0`, `ssff = 0.5`), source reading indicates that values entered in `temperature.cha` do not affect channel water temperature calculations at this commit.
{% endhint %}

# temperature.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [sno_mlt](sno_mlt.md) | Coefficient influencing the magnitude of snowmelt temperature contributions to the channel | real | none | 1.0 | — |
| [gw](gw.md) | Coefficient influencing the magnitude of groundwater temperature contributions to the channel | real | none | 1.0 | — |
| [sur_lat](sur_lat.md) | Coefficient influencing the magnitude of surface and lateral flow temperature contributions to the channel | real | none | 1.0 | — |
| [sno_lag](sno_lag.md) | Average air temperature lag, in days, applied to snowmelt temperature inputs | real | days | 2 | 1-3 |
| [gw_lag](gw_lag.md) | Average air temperature lag, in days, applied to groundwater temperature inputs | real | days | 250 | 200-365 |
| [surf_lag](surf_lag.md) | Average air temperature lag, in days, applied to surface runoff temperature inputs | real | days | 5 | 2-5 |
| [lat_lag](lat_lag.md) | Average air temperature lag, in days, applied to lateral flow temperature inputs | real | days | 10 | 5-10 |
| [lat_lag_coef](lat_lag_coef.md) | Coefficient applied to the lateral flow air temperature lag | real | none | 0.75 | — |
| [surf_lag_coef](surf_lag_coef.md) | Coefficient applied to the surface runoff air temperature lag; also applied to snow temperature lag | real | none | 0.75 | — |
| [gw_lag_coef](gw_lag_coef.md) | Coefficient applied to the groundwater air temperature lag | real | none | 0.75 | — |
| [hex_coef1](hex_coef1.md) | Coefficient used to calibrate the dew point temperature contribution | real | none | 0.75 | — |
| [hex_coef2](hex_coef2.md) | Coefficient used to calibrate channel geometry relationships | real | none | 1.5 | — |
| [sf_on](sf_on.md) | Activation flag for the shade factor file | integer | n/a | 0 | 0-1 |
| [ssff](ssff.md) | Default shade factor value used when the shade factor file is not active | real | none | 0.5 | 0-1 |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
