---
description: This file contains observed atmospheric deposition data.
---

# atmo.cli

SWAT+ is able to read in monthly, yearly, and average annual atmospheric deposition values. Reading in daily values is currently not an option in SWAT+.

The **atmo.cli** file is formatted differently than most other SWAT+ input files and its structure varies slightly depending on the time step of the data. As in all SWAT+ input files, the first line is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the atmospheric deposition stations.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num_sta](num-sta.md) | Number of stations included in the file | integer |  |  |  |
| [timestep](timestep.md) | Time step of the atmospheric deposition data | string |  |  |  |
| [mo_init](mo-init.md) | First month data is available for (0 for yearly and average annual data) | integer |  |  |  |
| [yr_init](yr-init.md) | First year data is available for (0 for average annual data) | integer |  |  |  |
| [num_aa](num_aa.md) | Number of months or years data is available for | integer |  |  |  |

Below, there will be 5 lines for each station included in the atmospheric deposition file. In the first of these, the name of the station will be specified. The name of the station is a primary key referenced by [atmo\_dep](../weather-sta.cli/atmo_dep.md) in [**weather-sta.cli**](../weather-sta.cli/). It is followed by 4 lines of data:

1. Wet deposition of ammonium nitrogen
2. Wet deposition of nitrate nitrogen
3. Dry deposition of ammonium nitrogen
4. Dry deposition of nitrate nitrogen

Each record contains one value in average annual mode and [num_aa](num_aa.md) values in monthly or yearly mode. The four rows are read in the order shown, including any zero values. See [cli_read_atmodep.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep.f90#L69-L119).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --- | --- | --- | --- | --- | --- |
| [station_name](station-name.md) | Atmospheric deposition station name | string |  |  |  |
| [nh4_rf](nh4-rf.md) | Ammonium nitrogen concentration in rainfall | real | mg/L |  |  |
| [no3_rf](no3-rf.md) | Nitrate nitrogen concentration in rainfall | real | mg/L |  |  |
| [nh4_dry](nh4-dry.md) | Dry ammonium nitrogen deposition per input period | real | kg/ha |  |  |
| [no3_dry](no3-dry.md) | Dry nitrate nitrogen deposition per input period | real | kg/ha |  |  |
