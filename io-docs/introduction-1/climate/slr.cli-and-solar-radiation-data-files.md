---
description: >-
  These files contain all information needed by the model about observed solar
  radiation data.
---

# slr.cli and slr data files

The **solar radiation data files** contain the observed precipitation input data. Use the exact filename listed in the corresponding climate list. A common extension is .slr. There must be one file per station used in the simulation. As in all SWAT+ input files, the first line in the solar radiation data files is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](slr/nbyr.md) | Length of the solar radiation time series | integer | years |  |  |
| [tstep](slr/tstep.md) | Time step of the solar radiation data | integer | n/a |  |  |
| [lat](slr/lat.md) | Latitude of the solar radiation station | real | Decimal Degrees |  |  |
| [lon](slr/lon.md) | Longitude of the solar radiation station | real | Decimal Degrees |  |  |
| [elev](slr/elev.md) | Elevation of the solar radiation station | real | m |  |  |

Starting in the fourth line, the year, Julian day, and solar radiation are listed. There are no headers for these columns.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](slr/year.md) | Year of the observation | integer | n/a |  |  |
| [jday](slr/jday.md) | Julian day of the observation | integer | n/a |  |  |
| [slr](slr/slr.md) | Observed solar radiation | real | MJ/m^2/day |  |  |

{% hint style="info" %}
Enter −99 for missing observations. SWAT+ uses the weather generator for values at or below −97 and dates outside the station coverage. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L64-L160).
{% endhint %}

The **slr.cli** file lists the names of the solar radiation data files used in the simulation. The first line is reserved for user comments. The second line is reserved for the column header "filename". The user can list as many solar radiation data file names as needed for the simulation. Only one file name should be listed per line. List each measured filename referenced for this variable in [weather-sta.cli](weather-sta.cli/README.md). For every file name listed in **slr.cli**, a file with that name must be provided by the user that contains the solar radiation data measured at the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [filename](slr/filename.md) | Name of the measured data file | string |  |  |  |
