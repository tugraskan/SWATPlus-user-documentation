# Routing unit constituent fluxes

Routing unit constituent output is written for each routing unit at daily, monthly, yearly, and average annual time steps. A period is active when the `print.prt` flag `pco%cs_ru%d`, `%m`, `%y`, or `%a` is `y` and `cs_db%num_cs > 0`. The daily file setup is nested under `sp_ob%ru > 0`. [Daily file setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L729-L760), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L768), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L806), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L844), [data writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L47-L293)

* rout\_unit\_cs\_day.txt
* rout\_unit\_cs\_day.csv
* rout\_unit\_cs\_mon.txt
* rout\_unit\_cs\_mon.csv
* rout\_unit\_cs\_yr.txt
* rout\_unit\_cs\_yr.csv
* rout\_unit\_cs\_aa.txt
* rout\_unit\_cs\_aa.csv

A `.csv` copy is written only when `pco%csvout == "y"`. [CSV condition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L757-L761)

* Each file starts with the basin name and `prog`, a title line, a definitions list, and one column-name row. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L732-L756)
* Every data row begins with six values: `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Then it holds sixteen groups of values in the table order below, each with one value per constituent (`cs_db%num_cs` values). [Data row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L48-L64)
* The column-name row is the fixed header record `rucsb_hdr`. It names three constituent columns for each group: `seo4`, `seo3`, and `born`. [Header record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L504-L576)
* The source comment on the `total` header names says total is surq + latq + tile, while the legend line says total is perc + surq + latq + tile. [Header comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L512), [legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L739)

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
| [jday](routing-unit/jday.md) | Julian day | integer | n/a |
| [mon](routing-unit/mon.md) | Month | integer | n/a |
| [day](routing-unit/day.md) | Day of the month | integer | n/a |
| [yr](routing-unit/yr.md) | Calendar year | integer | n/a |
| [unit](routing-unit/unit.md) | Routing unit number | integer | n/a |
| [gis\_id](routing-unit/gis_id.md) | GIS ID of the routing unit | integer | n/a |
| [total\_seo4, total\_seo3, total\_born](routing-unit/total.md) | Total constituent mass out | real | kg |
| [perc\_seo4, perc\_seo3, perc\_born](routing-unit/perc.md) | Mass in deep percolation (soil --> aquifer) | real | kg |
| [surq\_seo4, surq\_seo3, surq\_born](routing-unit/surq.md) | Mass in surface runoff (soil --> stream) | real | kg |
| [latq\_seo4, latq\_seo3, latq\_born](routing-unit/latq.md) | Mass in soil lateral flow (soil --> stream) | real | kg |
| [tile\_seo4, tile\_seo3, tile\_born](routing-unit/tile.md) | Mass in tile drainage (soil --> stream) | real | kg |
| [sedm\_seo4, sedm\_seo3, sedm\_born](routing-unit/sedm.md) | Mass in sediment runoff (soil --> stream) | real | kg |
| [wtsp\_seo4, wtsp\_seo3, wtsp\_born](routing-unit/wtsp.md) | Mass in wetland seepage (wetland --> soil) | real | kg |
| [irsw\_seo4, irsw\_seo3, irsw\_born](routing-unit/irsw.md) | Mass in surface water irrigation (channel --> soil) | real | kg |
| [irgw\_seo4, irgw\_seo3, irgw\_born](routing-unit/irgw.md) | Mass in groundwater irrigation (aquifer --> soil) | real | kg |
| [irwo\_seo4, irwo\_seo3, irwo\_born](routing-unit/irwo.md) | Mass in outside source irrigation (outside --> soil) | real | kg |
| [rain\_seo4, rain\_seo3, rain\_born](routing-unit/rain.md) | Mass in rainfall (outside --> soil) | real | kg |
| [dryd\_seo4, dryd\_seo3, dryd\_born](routing-unit/dryd.md) | Mass in dry deposition (outside --> soil) | real | kg |
| [fert\_seo4, fert\_seo3, fert\_born](routing-unit/fert.md) | Mass in applied fertilizer (outside --> soil) | real | kg |
| [uptk\_seo4, uptk\_seo3, uptk\_born](routing-unit/uptk.md) | Mass in plant uptake (soil --> outside) | real | kg |
| [rctn\_seo4, rctn\_seo3, rctn\_born](routing-unit/rctn.md) | Mass transferred via reaction (soil --> outside) | real | kg |
| [sorb\_seo4, sorb\_seo3, sorb\_born](routing-unit/sorb.md) | Mass transferred via sorption (soil --> sorbed mass) | real | kg |

## Reporting differences

* The file title ends in `daily`, `monthly`, `yearly`, or `average annaul`; the average annual title is spelled that way in the source. [Daily title](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L734), [average annual title](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L848)
* In the average annual legend, the unit is `kg/yr` instead of `kg`. [Average annual legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L853-L861)
* The daily, monthly, and yearly CSV files carry the heading line `all values in kg`. [Daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L760), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L798), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L836)
* Average annual rows divide every group by `time%nbyr`. Monthly and yearly rows write the accumulated daily values. [Average annual division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L257-L273), [monthly write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L105-L142)
