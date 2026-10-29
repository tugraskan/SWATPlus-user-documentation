# Plant and Weather

Plant and weather output can be printed at basin, LSU, HRU, and HRU-lte level by entering "y" in the _basin\_wb_, _lsunit\_wb_, _hru\_wb_, and _hru-lte\_wb_ lines in [**print.prt**](../../introduction-1/simulation-settings/print.prt), respectively. Plant and weather  output can be printed at daily, monthly, yearly, and average annual time steps. The names of the plant and weather  output files are as follows:&#x20;

* basin\_pw\_day.txt
* basin\_pw\_mon.txt
* basin\_pw\_yr.txt
* basin\_pw\_aa.txt
* lsunit\_pw\_day.txt
* lsunit\_pw\_mon.txt
* lsunit\_pw\_yr.txt
* lsunit\_pw\_aa.txt
* hru\_pw\_day.txt
* hru\_pw\_mon.txt
* hru\_pw\_yr.txt
* hru\_pw\_aa.txt
* hru-lte\_pw\_day.txt
* hru-lte\_pw\_mon.txt
* hru-lte\_pw\_yr.txt
* hru-lte\_pw\_aa.txt

Corresponding `.csv` files are written when CSV output is enabled. The shared printed header includes `plant_cov` and `mgt_ops`; those two trailing values are written only for HRU rows. Basin, LSU, and HRU-lte rows stop at `c_gro`.

<table><thead><tr><th width="136.6666259765625">Field</th><th width="263.33331298828125">Description</th><th width="108">Unit</th></tr></thead><tbody><tr><td><a href="plant-and-weather/jday.md">jday</a></td><td>Julian day</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/mon.md">mon</a></td><td>Month</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/day.md">day</a></td><td>Day of the month</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/yr.md">yr</a></td><td>Year</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/unit.md">unit</a></td><td>ID of the object</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/gis_id.md">gis_id</a></td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/name.md">name</a></td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/lai.md">lai</a></td><td>Average leaf area index</td><td>m2/m2</td></tr><tr><td><a href="plant-and-weather/bioms.md">bioms</a></td><td>Average total plant biomass</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/yield.md">yield</a></td><td>Harvested biomass yield (dry weight)</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/residue.md">residue</a></td><td>Average residue on surface</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/sol_tmp.md">sol_tmp</a></td><td>Average temperature of soil layer 2</td><td>deg C</td></tr><tr><td><a href="plant-and-weather/strsw.md">strsw</a></td><td>Water stress</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/strsa.md">strsa</a></td><td>Aeration stress</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/strstmp.md">strstmp</a></td><td>Temperature stress</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/strsn.md">strsn</a></td><td>Nitrogen stress</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/strsp.md">strsp</a></td><td>Phosphorus stress</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/strss.md">strss</a></td><td>Salt stress</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/nplt.md">nplt</a></td><td>Plant uptake of nitrogen</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/percn.md">percn</a></td><td>Nitrate nitrogen leached from bottom of soil profile</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/pplnt.md">pplnt</a></td><td>Plant uptake of phosphorus</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/tmx.md">tmx</a></td><td>Average maximum temperature</td><td>deg C</td></tr><tr><td><a href="plant-and-weather/tmn.md">tmn</a></td><td>Average minimum temperature</td><td>deg C</td></tr><tr><td><a href="plant-and-weather/tmpav.md">tmpav</a></td><td>Average mean temperature</td><td>deg C</td></tr><tr><td><a href="plant-and-weather/solarad.md">solarad</a></td><td>Average solar radiation</td><td>mJ/m2</td></tr><tr><td><a href="plant-and-weather/wndspd.md">wndspd</a></td><td>Average wind speed</td><td>m/s</td></tr><tr><td><a href="plant-and-weather/rhum.md">rhum</a></td><td>Average relative humidity</td><td>frac</td></tr><tr><td><a href="plant-and-weather/phubas0.md">phubas0</a></td><td><mark style="color:red;">Base zero potential heat units</mark></td><td>deg C/deg C</td></tr><tr><td><a href="plant-and-weather/lai_max.md">lai_max</a></td><td>Maximum leaf area index</td><td>m2/m2</td></tr><tr><td><a href="plant-and-weather/bm_max.md">bm_max</a></td><td>Maximum total plant biomass</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/bm_grow.md">bm_grow</a></td><td>Total plant biomass growth </td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/c_gro.md">c_gro</a></td><td>Total plant carbon growth</td><td>kg/ha</td></tr><tr><td><a href="plant-and-weather/plant_cov.md">plant_cov</a></td><td>Plant-cover label written for HRU rows</td><td>n/a</td></tr><tr><td><a href="plant-and-weather/mgt_ops.md">mgt_ops</a></td><td>Management-operation label written for HRU rows</td><td>n/a</td></tr></tbody></table>

## Crop yield reports

Crop-yield output is yearly or average annual rather than daily or monthly.

- `basin_crop_yld_yr.txt` and `basin_crop_yld_aa.txt` print `year`, `plant_no`, `plant_name`, `harv_area(ha)`, `yld(t)`, and `yld(t/ha)`.
- `crop_yld_yr.txt` and `crop_yld_aa.txt` print `jday`, `mon`, `day`, `yr`, `unit`, `PLANTNM`, `MASS`, `C`, `N`, and `P`.
- The corresponding HRU CSV header is shorter and prints `jday`, `mon`, `day`, `year`, `unit`, `plantnm`, and `yield`.

The TXT and CSV crop-yield headings are therefore not interchangeable.

