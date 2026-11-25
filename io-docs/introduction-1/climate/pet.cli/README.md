---
description: "This file lists potential evapotranspiration data files for climate stations."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists potential evapotranspiration data files for climate stations.

# pet.cli

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [filename](filename.md) | Name of the file containing potential evapotranspiration input data for the associated climate station | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.

The list file starts with a title and header. Each referenced file starts with a title, header and station metadata row, followed by daily observations. See [cli_petmeas.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_petmeas.f90#L78-L83) and [cli_petmeas.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_petmeas.f90#L112-L124).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [nbyr](nbyr.md) | Number of years | integer | years |  |  |
| [tstep](tstep.md) | Time-step field | integer |  |  |  |
| [lat](lat.md) | Latitude | real | decimal degrees |  |  |
| [lon](lon.md) | Longitude | real | decimal degrees |  |  |
| [elev](elev.md) | Elevation | real | m |  |  |

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [year](year.md) | Calendar year | integer |  |  |  |
| [jday](jday.md) | Day of year | integer |  |  |  |
| [pet](pet.md) | Daily potential evapotranspiration | real | mm/day |  |  |

SWAT+ reads measured PET for matched stations, then recomputes station PET with Hargreaves for every weather station and applies a minimum of 0.01 mm/day. HRU PET method 3 uses this recomputed value before applying the HRU PET coefficient. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L165-L210) and [et_pot.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L273-L280).

For $T_{\max}>T_{\min}$, the station calculation uses:

$$
\mathrm{PET}=\max\!\left(0.01,\ 0.0023\frac{37.59R_{\max}}{30(2.501-0.002361T_{\mathrm{ave}})}(T_{\mathrm{ave}}+17.8)\sqrt{T_{\max}-T_{\min}}\right)
$$

where:

- $\mathrm{PET}$ is the station potential evapotranspiration (mm/day),
- $R_{\max}$ is maximum solar radiation (MJ/m²/day),
- $T_{\mathrm{ave}}$ is daily mean air temperature (°C),
- $T_{\max}$ is daily maximum air temperature (°C), and
- $T_{\min}$ is daily minimum air temperature (°C).

If $T_{\max}\leq T_{\min}$, station PET is 0.01 mm/day. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L199-L210).
