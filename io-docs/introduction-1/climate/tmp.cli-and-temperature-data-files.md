---
description: >-
  These files contain all information needed by the model about observed
  temperature data.
---

# tmp.cli and tmp data files

The **temperature data files** contain the observed temperature input data. Use the exact filename listed in the corresponding climate list. A common extension is .tmp. There must be one file per station used in the simulation. As in all SWAT+ input files, the first line in the temperature data files is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](tmp/nbyr.md) | Length of the temperature time series | integer | years |  |  |
| [tstep](tmp/tstep.md) | Time step of the temperature data | integer | n/a |  |  |
| [lat](tmp/lat.md) | Latitude of the temperature station | real | Decimal Degrees |  |  |
| [lon](tmp/lon.md) | Longitude of the temperature station | real | Decimal Degrees |  |  |
| [elev](tmp/elev.md) | Elevation of the temperature station | real | m |  |  |

Starting in the fourth line, the year, Julian day, and the maximum and minimum temperatures are listed. There are no headers for these columns.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](tmp/year.md) | Year of the observation | integer | n/a |  |  |
| [jday](tmp/jday.md) | Julian day of the observation | integer | n/a |  |  |
| [tmpmax](tmp/tmpmax.md) | Observed maximum temperature | real | °C |  |  |
| [tmpmin](tmp/tmpmin.md) | Observed minimum temperature | real | °C |  |  |

{% hint style="info" %}
Enter −99 for missing observations. SWAT+ uses the weather generator for values at or below −97 and dates outside the station coverage. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L64-L160).
{% endhint %}

The **tmp.cli** file lists the names of the temperature data files used in the simulation. The first line is reserved for user comments. The second line is reserved for the column header "filename". The user can list as many temperature data file names as needed for the simulation. Only one file name should be listed per line. List each measured filename referenced for this variable in [weather-sta.cli](weather-sta.cli/README.md). For every file name listed in **tmp.cli**, a file with that name must be provided by the user that contains the temperature data measured at the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [filename](tmp/filename.md) | Name of the measured data file | string |  |  |  |
