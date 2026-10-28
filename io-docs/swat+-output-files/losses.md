# Losses

Losses output can be printed at basin, LSU, HRU, and HRU-lte level by entering "y" in the _basin\_wb_, _lsunit\_wb_, _hru\_wb_, and _hru-lte\_wb_ lines in [print.prt](../introduction-1/simulation-settings/print.prt/), respectively. Losses output can be printed at daily, monthly, yearly, and average annual time steps. The names of the losses output files are as follows:&#x20;

* basin\_ls\_day.txt
* basin\_ls\_mon.txt
* basin\_ls\_yr.txt
* basin\_ls\_aa.txt
* lsunit\_ls\_day.txt
* lsunit\_ls\_mon.txt
* lsunit\_ls\_yr.txt
* lsunit\_ls\_aa.txt
* hru\_ls\_day.txt
* hru\_ls\_mon.txt
* hru\_ls\_yr.txt
* hru\_ls\_aa.txt
* <mark style="color:red;">hru-lte\_ls\_day.txt</mark>
* <mark style="color:red;">hru-lte\_ls\_mon.txt</mark>
* <mark style="color:red;">hru-lte\_ls\_yr.txt</mark>
* <mark style="color:red;">hru-lte\_ls\_aa.txt</mark>

Corresponding `.csv` files are written when CSV output is enabled. The shared printed header includes `plant_cov`, `mgt_ops`, and `percn`; those three trailing values are written only for HRU rows. Basin, LSU, and HRU-lte rows stop at `satexn`.

<table><thead><tr><th width="133.33331298828125">Field</th><th width="276.66668701171875">Description</th><th width="103.3333740234375">Unit</th></tr></thead><tbody><tr><td>jday</td><td>Julian day</td><td>n/a</td></tr><tr><td>mon</td><td>Month</td><td>n/a</td></tr><tr><td>day</td><td>Day of the month</td><td>n/a</td></tr><tr><td>yr</td><td>Year</td><td>n/a</td></tr><tr><td>unit</td><td>ID of the object</td><td>n/a</td></tr><tr><td>gis_id</td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td>name</td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td>sedyld</td><td>Sediment yield leaving the landscape through water erosion</td><td>t/ha</td></tr><tr><td>sedorgn</td><td>Organic nitrogen transported in surface runoff</td><td>kg/ha</td></tr><tr><td>sedorgp</td><td>Organic phosphorus transported in surface runoff</td><td>kg/ha</td></tr><tr><td>surqno3</td><td>Nitrate nitrogen transported in surface runoff</td><td>kg/ha</td></tr><tr><td>lat3no3</td><td>Nitrate nitrogen transported in lateral flow</td><td>kg/ha</td></tr><tr><td>surqsolp</td><td>Soluble phosphorus transported in surface runoff</td><td>kg/ha</td></tr><tr><td>usle</td><td>Sediment yield predicted with the USLE equation</td><td>t/ha</td></tr><tr><td>sedminp</td><td>Mineral phosphorus leaving the landscape attached to sediment</td><td>kg/ha</td></tr><tr><td>tileno3</td><td>Nitrate nitrogen transported in tile flow</td><td>kg/ha</td></tr><tr><td>lchlabp</td><td>Soluble (labile) phosphorus leaching past bottom soil layer</td><td>kg/ha</td></tr><tr><td>tilelabp</td><td>Soluble (labile) phosphorus in tile flow</td><td>kg/ha</td></tr><tr><td>satexn</td><td>Nitrate nitrogen in saturation excess surface runoff</td><td>kg/ha</td></tr><tr><td>plant_cov</td><td>Plant-cover label written for HRU rows</td><td>n/a</td></tr><tr><td>mgt_ops</td><td>Management-operation label written for HRU rows</td><td>n/a</td></tr><tr><td>percn</td><td>Nitrate nitrogen transported by percolation</td><td>kg/ha</td></tr></tbody></table>
