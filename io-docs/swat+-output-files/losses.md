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

<table><thead><tr><th width="133.33331298828125">Field</th><th width="276.66668701171875">Description</th><th width="103.3333740234375">Unit</th></tr></thead><tbody><tr><td><a href="losses/jday.md">jday</a></td><td>Julian day</td><td>n/a</td></tr><tr><td><a href="losses/mon.md">mon</a></td><td>Month</td><td>n/a</td></tr><tr><td><a href="losses/day.md">day</a></td><td>Day of the month</td><td>n/a</td></tr><tr><td><a href="losses/yr.md">yr</a></td><td>Year</td><td>n/a</td></tr><tr><td><a href="losses/unit.md">unit</a></td><td>ID of the object</td><td>n/a</td></tr><tr><td><a href="losses/gis_id.md">gis_id</a></td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td><a href="losses/name.md">name</a></td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td><a href="losses/sedyld.md">sedyld</a></td><td>Sediment yield leaving the landscape through water erosion</td><td>t/ha</td></tr><tr><td><a href="losses/sedorgn.md">sedorgn</a></td><td>Organic nitrogen transported in surface runoff</td><td>kg/ha</td></tr><tr><td><a href="losses/sedorgp.md">sedorgp</a></td><td>Organic phosphorus transported in surface runoff</td><td>kg/ha</td></tr><tr><td><a href="losses/surqno3.md">surqno3</a></td><td>Nitrate nitrogen transported in surface runoff</td><td>kg/ha</td></tr><tr><td><a href="losses/lat3no3.md">lat3no3</a></td><td>Nitrate nitrogen transported in lateral flow</td><td>kg/ha</td></tr><tr><td><a href="losses/surqsolp.md">surqsolp</a></td><td>Soluble phosphorus transported in surface runoff</td><td>kg/ha</td></tr><tr><td><a href="losses/usle.md">usle</a></td><td>Sediment yield predicted with the USLE equation</td><td>t/ha</td></tr><tr><td><a href="losses/sedminp.md">sedminp</a></td><td>Mineral phosphorus leaving the landscape attached to sediment</td><td>kg/ha</td></tr><tr><td><a href="losses/tileno3.md">tileno3</a></td><td>Nitrate nitrogen transported in tile flow</td><td>kg/ha</td></tr><tr><td><a href="losses/lchlabp.md">lchlabp</a></td><td>Soluble (labile) phosphorus leaching past bottom soil layer</td><td>kg/ha</td></tr><tr><td><a href="losses/tilelabp.md">tilelabp</a></td><td>Soluble (labile) phosphorus in tile flow</td><td>kg/ha</td></tr><tr><td><a href="losses/satexn.md">satexn</a></td><td>Nitrate nitrogen in saturation excess surface runoff</td><td>kg/ha</td></tr><tr><td><a href="losses/plant_cov.md">plant_cov</a></td><td>Plant-cover label written for HRU rows</td><td>n/a</td></tr><tr><td><a href="losses/mgt_ops.md">mgt_ops</a></td><td>Management-operation label written for HRU rows</td><td>n/a</td></tr><tr><td><a href="losses/percn.md">percn</a></td><td>Nitrate nitrogen transported by percolation</td><td>kg/ha</td></tr></tbody></table>
