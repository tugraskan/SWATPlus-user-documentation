---
description: >-
  These files contain all information needed by the model about observed
  temperature data.
---

# tmp.cli and tmp data files

The **temperature data files** contain the observed temperature input data. They are named by the user and must have the file ending \*.tmp. There must be one file per station used in the simulation. As in all SWAT+ input files, the first line in the temperature data files is reserved for user comments. The second line contains the column headers for the third line, which lists basic information about the station.&#x20;

<table><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th><th>Unit</th></tr></thead><tbody><tr><td>nbyr</td><td>Length of the temperature time series</td><td>integer</td><td>years</td></tr><tr><td>tstep</td><td>Time step of the temperature data</td><td>integer</td><td>n/a</td></tr><tr><td>lat</td><td>Latitude of the temperature station</td><td>real</td><td>Decimal Degrees</td></tr><tr><td>lon</td><td>Longitude of the temperature station</td><td>real</td><td>Decimal Degrees</td></tr><tr><td>elev</td><td>Elevation of the temperature station</td><td>real</td><td>m</td></tr></tbody></table>

Starting in the fourth line, the year, Julian day, and the maximum and minimum temperatures are listed. There are no headers for these columns.

<table><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th><th>Unit</th></tr></thead><tbody><tr><td>year</td><td>Year of the observation</td><td>integer</td><td>n/a</td></tr><tr><td>jday</td><td>Julian day of the observation</td><td>integer</td><td>n/a</td></tr><tr><td>tmpmax</td><td>Observed maximum temperature</td><td>real</td><td>°C</td></tr><tr><td>tmpmin</td><td>Observed minimum temperature</td><td>real</td><td>°C</td></tr></tbody></table>

{% hint style="info" %}
A negative 99.0 (-99.0) should be inserted for missing data. This value tells SWAT+ to generate minimum and maximum temperatures for that day.
{% endhint %}

The **tmp.cli** file lists the names of the temperature data files used in the simulation. The first line is reserved for user comments. The second line is reserved for the column header "filename". The user can list as many temperature data file names as needed for the simulation. Only one file name should be listed per line. All file names listed in [**weather-sta.cli**](weather-sta.cli/) must be listed here. For every file name listed in **tmp.cli**, a file with that name must be provided by the user that contains the temperature data measured at the station. &#x20;
