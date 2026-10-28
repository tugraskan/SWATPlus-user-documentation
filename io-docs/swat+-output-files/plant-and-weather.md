# Plant and Weather

Plant and weather output can be printed at basin, LSU, HRU, and HRU-lte level by entering "y" in the _basin\_wb_, _lsunit\_wb_, _hru\_wb_, and _hru-lte\_wb_ lines in [**print.prt**](../introduction-1/simulation-settings/print.prt/), respectively. Plant and weather  output can be printed at daily, monthly, yearly, and average annual time steps. The names of the plant and weather  output files are as follows:&#x20;

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

<table><thead><tr><th width="136.6666259765625">Field</th><th width="263.33331298828125">Description</th><th width="108">Unit</th></tr></thead><tbody><tr><td>jday</td><td>Julian day</td><td>n/a</td></tr><tr><td>mon</td><td>Month</td><td>n/a</td></tr><tr><td>day</td><td>Day of the month</td><td>n/a</td></tr><tr><td>yr</td><td>Year</td><td>n/a</td></tr><tr><td>unit</td><td>ID of the object</td><td>n/a</td></tr><tr><td>gis_id</td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td>name</td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td>lai</td><td>Average leaf area index</td><td>m2/m2</td></tr><tr><td>bioms</td><td>Average total plant biomass</td><td>kg/ha</td></tr><tr><td>yield</td><td>Harvested biomass yield (dry weight)</td><td>kg/ha</td></tr><tr><td>residue</td><td>Average residue on surface</td><td>kg/ha</td></tr><tr><td>sol_tmp</td><td>Average temperature of soil layer 2</td><td>deg C</td></tr><tr><td>strsw</td><td>Water stress</td><td>n/a</td></tr><tr><td>strsa</td><td>Aeration stress</td><td>n/a</td></tr><tr><td>strstmp</td><td>Temperature stress</td><td>n/a</td></tr><tr><td>strsn</td><td>Nitrogen stress</td><td>n/a</td></tr><tr><td>strsp</td><td>Phosphorus stress</td><td>n/a</td></tr><tr><td>strss</td><td>Salt stress</td><td>n/a</td></tr><tr><td>nplt</td><td>Plant uptake of nitrogen</td><td>kg/ha</td></tr><tr><td>percn</td><td>Nitrate nitrogen leached from bottom of soil profile</td><td>kg/ha</td></tr><tr><td>pplnt</td><td>Plant uptake of phosphorus</td><td>kg/ha</td></tr><tr><td>tmx</td><td>Average maximum temperature</td><td>deg C</td></tr><tr><td>tmn</td><td>Average minimum temperature</td><td>deg C</td></tr><tr><td>tmpav</td><td>Average mean temperature</td><td>deg C</td></tr><tr><td>solarad</td><td>Average solar radiation</td><td>mJ/m2</td></tr><tr><td>wndspd</td><td>Average wind speed</td><td>m/s</td></tr><tr><td>rhum</td><td>Average relative humidity</td><td>frac</td></tr><tr><td>phubas0</td><td><mark style="color:red;">Base zero potential heat units</mark></td><td>deg C/deg C</td></tr><tr><td>lai_max</td><td>Maximum leaf area index</td><td>m2/m2</td></tr><tr><td>bm_max</td><td>Maximum total plant biomass</td><td>kg/ha</td></tr><tr><td>bm_grow</td><td>Total plant biomass growth </td><td>kg/ha</td></tr><tr><td>c_gro</td><td>Total plant carbon growth</td><td>kg/ha</td></tr><tr><td>plant_cov</td><td>Plant-cover label written for HRU rows</td><td>n/a</td></tr><tr><td>mgt_ops</td><td>Management-operation label written for HRU rows</td><td>n/a</td></tr></tbody></table>

## Crop yield reports

Crop-yield output is yearly or average annual rather than daily or monthly.

- `basin_crop_yld_yr.txt` and `basin_crop_yld_aa.txt` print `year`, `plant_no`, `plant_name`, `harv_area(ha)`, `yld(t)`, and `yld(t/ha)`.
- `crop_yld_yr.txt` and `crop_yld_aa.txt` print `jday`, `mon`, `day`, `yr`, `unit`, `PLANTNM`, `MASS`, `C`, `N`, and `P`.
- The corresponding HRU CSV header is shorter and prints `jday`, `mon`, `day`, `year`, `unit`, `plantnm`, and `yield`.

The TXT and CSV crop-yield headings are therefore not interchangeable.

