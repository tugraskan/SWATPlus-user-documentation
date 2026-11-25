---
description: >-
  These files contain all information needed by the model about observed
  relative humidity data.
---

# hmd.cli and hmd data files

The **relative humidity data files** contain the observed relative humidity input data. Use the exact filename listed in the corresponding climate list. A common extension is .hmd. There must be one file per station used in the simulation. As in all SWAT+ input files, the first line in the relative humidity data files is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](hmd/nbyr.md) | Length of the relative humidity time series | integer | years |  |  |
| [tstep](hmd/tstep.md) | Time step of the relative humidity data | integer | n/a |  |  |
| [lat](hmd/lat.md) | Latitude of the relative humidity station | real | Decimal Degrees |  |  |
| [lon](hmd/lon.md) | Longitude of the relative humidity station | real | Decimal Degrees |  |  |
| [elev](hmd/elev.md) | Elevation of the relative humidity station | real | m |  |  |

Starting in the fourth line, the year, Julian day, and the relative humidity are listed. There are no headers for these columns.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](hmd/year.md) | Year of the observation | integer | n/a |  |  |
| [jday](hmd/jday.md) | Julian day of the observation | integer | n/a |  |  |
| [hmd](hmd/hmd.md) | Observed relative humidity | real | fraction |  |  |

{% hint style="info" %}
Enter −99 for missing observations. SWAT+ uses the weather generator for values at or below −97 and dates outside the station coverage. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L64-L160).
{% endhint %}

The **hmd.cli** file lists the names of the relative humidity data files used in the simulation. The first line is reserved for user comments. The second line is reserved for the column header "filename". The user can list as many relative humidity data file names as needed for the simulation. Only one file name should be listed per line. List each measured filename referenced for this variable in [weather-sta.cli](weather-sta.cli/README.md). For every file name listed in **hmd.cli**, a file with that name must be provided by the user that contains the relative humidity data measured at the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [filename](hmd/filename.md) | Name of the measured data file | string |  |  |  |
