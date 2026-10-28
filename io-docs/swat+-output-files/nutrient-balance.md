# Nutrient Balance

Nutrient balance output can be printed at basin, LSU, HRU, and HRU-lte level by entering "y" in the _basin\_nb_, _lsunit\_nb_, _hru\_nb_, and _hru-lte\_nb_ lines in [print.prt](../introduction-1/simulation-settings/print.prt/), respectively. Nutrient balance output can be printed at daily, monthly, yearly, and average annual time steps. The names of the nutrient balance output files are as follows:&#x20;

* basin\_nb\_day.txt
* basin\_nb\_mon.txt
* basin\_nb\_yr.txt
* basin\_nb\_aa.txt
* lsunit\_nb\_day.txt
* lsunit\_nb\_mon.txt
* lsunit\_nb\_yr.txt
* lsunit\_nb\_aa.txt
* hru\_nb\_day.txt
* hru\_nb\_mon.txt
* hru\_nb\_yr.txt
* hru\_nb\_aa.txt

Corresponding `.csv` files are written when CSV output is enabled. The printed header also includes `plant_cov` and `mgt_ops`; those two trailing values are written for HRU rows but not for the basin and LSU rows.

<table><thead><tr><th width="149.3333740234375">Field</th><th width="252.66668701171875">Description</th><th width="115.3333740234375">Unit</th></tr></thead><tbody><tr><td>jday</td><td>Julian day</td><td>n/a</td></tr><tr><td>mon</td><td>Month</td><td>n/a</td></tr><tr><td>day</td><td>Day of the month</td><td>n/a</td></tr><tr><td>yr</td><td>Year</td><td>n/a</td></tr><tr><td>unit</td><td>ID of the object</td><td>n/a</td></tr><tr><td>gis_id</td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td>name</td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td>grzn</td><td>Total nitrogen added to soil from grazing</td><td>kg/ha</td></tr><tr><td>grzp</td><td>Total phosphorus added to soil from grazing</td><td>kg/ha</td></tr><tr><td>lab_min_p</td><td>Phosphorus moving from the labile mineral pool to the active mineral pool</td><td>kg/ha</td></tr><tr><td>act_sta_p</td><td>Phosphorus moving from the active mineral pool to the stable mineral pool</td><td>kg/ha</td></tr><tr><td>fertn</td><td>Total nitrogen applied to soil through fertilization</td><td>kg/ha</td></tr><tr><td>fertp</td><td>Total phosphorus applied to soil through fertilization</td><td>kg/ha</td></tr><tr><td>fixn</td><td>Nitrogen added to plant biomass via fixation</td><td>kg/ha</td></tr><tr><td>denit</td><td>Nitrogen lost from nitrate pool by denitrification</td><td>kg/ha</td></tr><tr><td>act_nit_n</td><td>Nitrogen moving from active organic pool to nitrate pool</td><td>kg/ha</td></tr><tr><td>act_sta_n</td><td>Nitrogen moving from active organic pool to stable pool</td><td>kg/ha</td></tr><tr><td>org_lab_p</td><td>Phosphorus moving from the organic pool to labile pool</td><td>kg/ha</td></tr><tr><td>rsd_nitorg_n</td><td>Nitrogen moving from the fresh organic pool (residue) to the nitrate (80%) and active organic (20%) pools</td><td>kg/ha</td></tr><tr><td>rsd_laborg_p</td><td>Phosphorus moving from the fresh organic pool (residue) to the labile (80%) and organic (20%) pools</td><td>kg/ha</td></tr><tr><td>no3atmo</td><td>Nitrate added to the soil from atmospheric deposition</td><td>kg/ha</td></tr><tr><td>nh4atmo</td><td>Ammonia added to the soil from atmospheric deposition</td><td>kg/ha</td></tr><tr><td>nuptake</td><td>Plant nitrogen uptake</td><td>kg/ha</td></tr><tr><td>puptake</td><td>Plant phosphorus uptake</td><td>kg/ha</td></tr><tr><td>gwsoiln</td><td>Nitrogen transferred from the aquifer to the soil by the GWFlow module</td><td>kg/ha</td></tr><tr><td>gwsoilp</td><td>Phosphorus transferred from the aquifer to the soil by the GWFlow module</td><td>kg/ha</td></tr><tr><td>plant_cov</td><td>Plant-cover label written for HRU rows</td><td>n/a</td></tr><tr><td>mgt_ops</td><td>Management-operation label written for HRU rows</td><td>n/a</td></tr></tbody></table>
