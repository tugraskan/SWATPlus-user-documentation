---
description: This file contains observed atmospheric deposition data.
---

# atmo.cli

SWAT+ is able to read in monthly, yearly, and average annual atmospheric deposition values. Reading in daily values is currently not an option in SWAT+.&#x20;

The **atmo.cli** file is formatted differently than most other SWAT+ input files and its structure varies slightly depending on the time step of the data. As in all SWAT+ input files, the first line is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the atmospheric deposition stations. &#x20;

<table><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th></tr></thead><tbody><tr><td>num_sta</td><td>Number of stations included in the file</td><td>integer</td></tr><tr><td><a href="timestep.md">timestep</a></td><td>Time step of the atmospheric deposition data</td><td>integer</td></tr><tr><td>mo_init</td><td>First month data is available for (0 for yearly and average annual data)</td><td>integer</td></tr><tr><td>yr_init</td><td>First year data is available for (0 for average annual data)</td><td>integer</td></tr><tr><td><a href="num_aa.md">num_aa</a></td><td>Number of months or years data is available for</td><td>integer</td></tr></tbody></table>

Below, there will be 5 lines for each station included in the atmospheric deposition file. In the first of these, the name of the station will be specified. The name of the station is a primary key referenced by [atmo\_dep](../weather-sta.cli/atmo_dep.md) in [**weather-sta.cli**](../weather-sta.cli/). It is followed by 4 lines of data:

1. Wet deposition of ammonia nitrogen
2. Wet deposition of nitrate nitrogen
3. Dry deposition of ammonia nitrogen
4. Dry deposition of nitrate nitrogen

The number of values listed in the data lines depends on the number of months or years data is available for. If average annual data is used, only one value will be listed.
