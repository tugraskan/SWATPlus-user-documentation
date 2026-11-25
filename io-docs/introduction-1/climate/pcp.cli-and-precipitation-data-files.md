---
description: >-
  These files contain all information needed by the model about observed
  precipitation data.
---

# pcp.cli and pcp data files

The **precipitation data files** contain the observed precipitation input data. Use the exact filename listed in the corresponding climate list. A common extension is .pcp. There must be one file per station used in the simulation. As in all SWAT+ input files, the first line in the precipitation data files is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](pcp/nbyr.md) | Length of the precipitation time series | integer | years |  |  |
| [tstep](pcp/tstep.md) | Time step of the precipitation data | integer | n/a |  |  |
| [lat](pcp/lat.md) | Latitude of the precipitation station | real | Decimal Degrees |  |  |
| [lon](pcp/lon.md) | Longitude of the precipitation station | real | Decimal Degrees |  |  |
| [elev](pcp/elev.md) | Elevation of the precipitation station | real | m |  |  |

Starting in the fourth line, the year, Julian day, and precipitation amount are listed. There are no headers for these columns.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](pcp/year.md) | Year of the observation | integer | n/a |  |  |
| [jday](pcp/jday.md) | Julian day of the observation | integer | n/a |  |  |
| [pcp](pcp/pcp.md) | Observed precipitation | real | mm |  |  |

For measured subdaily precipitation, provide one observation per simulation step and set a positive [tstep](pcp/tstep.md). SWAT+ reads three additional fields and stores the rows in input order within each day.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](pcp/year.md) | Year of the observation | integer | n/a |  |  |
| [jday](pcp/jday.md) | Julian day of the observation | integer | n/a |  |  |
| [mon](pcp/mon.md) | Month of the observation | integer | n/a |  |  |
| [day](pcp/day.md) | Day of the observation | integer | n/a |  |  |
| [hr](pcp/hr.md) | Time of the observation | integer | n/a |  |  |
| [pcp](pcp/pcp.md) | Observed precipitation | real | mm |  |  |

{% hint style="info" %}
For daily precipitation, enter −99 for missing observations. Values at or below −97 and dates outside the station coverage trigger generation. In the subdaily branch, a suspected model defect overwrites the generated daily total with the sum of the measured intervals, and a measured-array read overwrites the out-of-coverage marker. See [cli_precip_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_precip_control.f90#L73-L114).
{% endhint %}

The **pcp.cli** file lists the names of the precipitation data files used in the simulation. The first line is reserved for user comments. The second line is reserved for the column header "filename". The user can list as many precipitation data file names as needed for the simulation. Only one file name should be listed per line. List each measured filename referenced for this variable in [weather-sta.cli](weather-sta.cli/README.md). For every file name listed in **pcp.cli**, a file with that name must be provided by the user that contains the precipitation data measured at the station.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [filename](pcp/filename.md) | Name of the measured data file | string |  |  |  |
