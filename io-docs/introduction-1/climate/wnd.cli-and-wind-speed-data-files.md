---
description: >-
  These files contain all information needed by the model about observed wind
  speed data.
---

# wnd.cli and wnd data files

The **wind speed data files** contain the observed precipitation input data. Use the exact filename listed in the corresponding climate list. A common extension is .wnd. There must be one file per station used in the simulation. As in all SWAT+ input files, the first line in the wind speed data files is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](wnd/nbyr.md) | Length of the wind speed time series | integer | years |  |  |
| [tstep](wnd/tstep.md) | Time step of the wind speed data | integer | n/a |  |  |
| [lat](wnd/lat.md) | Latitude of the wind speed station | real | Decimal Degrees |  |  |
| [lon](wnd/lon.md) | Longitude of the wind speed station | real | Decimal Degrees |  |  |
| [elev](wnd/elev.md) | Elevation of the wind speed station | real | m |  |  |

Starting in the fourth line, the year, Julian day, and wind speed are listed. There are no headers for these columns.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](wnd/year.md) | Year of the observation | integer | n/a |  |  |
| [jday](wnd/jday.md) | Julian day of the observation | integer | n/a |  |  |
| [wnd](wnd/wnd.md) | Observed wind speed | real | m/s |  |  |

{% hint style="info" %}
Enter −99 for missing observations. SWAT+ uses the weather generator for values at or below −97 and dates outside the station coverage. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L64-L160).
{% endhint %}

The **wnd.cli** file lists the names of the wind speed data files used in the simulation. The first line is reserved for user comments. The second line is reserved for the column header "filename". The user can list as many wind speed data file names as needed for the simulation. Only one file name should be listed per line. List each measured filename referenced for this variable in [weather-sta.cli](weather-sta.cli/README.md). For every file name listed in **wnd.cli**, a file with that name must be provided by the user that contains the wind speed data measured at the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [filename](wnd/filename.md) | Name of the measured data file | string |  |  |  |
