# HRU constituent fluxes and state variables

HRU constituent output is written for each HRU at daily, monthly, yearly, and average annual time steps. Each period is controlled by its `print.prt` flag, `pco%cs_hru%d`, `%m`, `%y`, or `%a`, which must be `y`, and by `cs_db%num_cs > 0`. [Daily and monthly file setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L189-L266), [yearly and average annual file setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L271-L348), [data writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L48-L369)

* hru\_cs\_day.txt
* hru\_cs\_day.csv
* hru\_cs\_mon.txt
* hru\_cs\_mon.csv
* hru\_cs\_yr.txt
* hru\_cs\_yr.csv
* hru\_cs\_aa.txt
* hru\_cs\_aa.csv

A `.csv` copy is written only when `pco%csvout == "y"`, and it carries the same values as the `.txt` file. [CSV condition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L221)

* Each file starts with the basin name and `prog`, a title line, a definitions list, and then one column-name row. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L191-L220)
* Every data row begins with six values: `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Then it holds twenty groups of values in the table order below. Each group has one value for each constituent, so a group has `cs_db%num_cs` values. [Data row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L49-L69)
* The column-name row is the fixed header record `cs_hdr_hru`. It names three constituent columns for each group: `seo4`, `seo3`, and `born`. [Header record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L180-L271)
* The header record also names three `gwup_` columns between the `perc_` and `wtsp_` groups, but the data write has no value for them. The groups after `perc` therefore do not line up with the header names from that point on. [gwup header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L219-L222), [data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L57-L58)
* In the CSV files the heading line reads `conc = mg/L; other = kg/ha`, while the `.txt` legend gives `conc` in g/m3. [CSV heading](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L224)

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
| [jday](hru/jday.md) | Julian day | integer | n/a |
| [mon](hru/mon.md) | Month | integer | n/a |
| [day](hru/day.md) | Day of the month | integer | n/a |
| [yr](hru/yr.md) | Calendar year | integer | n/a |
| [unit](hru/unit.md) | HRU number | integer | n/a |
| [gis\_id](hru/gis_id.md) | GIS ID of the HRU | integer | n/a |
| [sl\_seo4, sl\_seo3, sl\_born](hru/sl.md) | Total mass in soil profile | real | kg/ha |
| [surq\_seo4, surq\_seo3, surq\_born](hru/surq.md) | Mass in surface runoff (soil --> stream) | real | kg/ha |
| [sedm\_seo4, sedm\_seo3, sedm\_born](hru/sedm.md) | Mass in sediment runoff (soil --> stream) | real | kg/ha |
| [latq\_seo4, latq\_seo3, latq\_born](hru/latq.md) | Mass in soil lateral flow (soil --> stream) | real | kg/ha |
| [urbq\_seo4, urbq\_seo3, urbq\_born](hru/urbq.md) | Mass in urban runoff (soil --> stream) | real | kg/ha |
| [wetq\_seo4, wetq\_seo3, wetq\_born](hru/wetq.md) | Mass in wetland runoff (wetland --> stream) | real | kg/ha |
| [tile\_seo4, tile\_seo3, tile\_born](hru/tile.md) | Mass in tile drainage (soil --> stream) | real | kg/ha |
| [perc\_seo4, perc\_seo3, perc\_born](hru/perc.md) | Mass in deep percolation (soil --> aquifer) | real | kg/ha |
| [wtsp\_seo4, wtsp\_seo3, wtsp\_born](hru/wtsp.md) | Mass in wetland seepage (wetland --> soil) | real | kg/ha |
| [irsw\_seo4, irsw\_seo3, irsw\_born](hru/irsw.md) | Mass in surface water irrigation (channel --> soil) | real | kg/ha |
| [irgw\_seo4, irgw\_seo3, irgw\_born](hru/irgw.md) | Mass in groundwater irrigation (aquifer --> soil) | real | kg/ha |
| [irwo\_seo4, irwo\_seo3, irwo\_born](hru/irwo.md) | Mass in outside source irrigation (outside --> soil) | real | kg/ha |
| [rain\_seo4, rain\_seo3, rain\_born](hru/rain.md) | Mass in rainfall (outside --> soil) | real | kg/ha |
| [dryd\_seo4, dryd\_seo3, dryd\_born](hru/dryd.md) | Mass in dry deposition (outside --> soil) | real | kg/ha |
| [fert\_seo4, fert\_seo3, fert\_born](hru/fert.md) | Mass in applied fertilizer (outside --> soil) | real | kg/ha |
| [uptk\_seo4, uptk\_seo3, uptk\_born](hru/uptk.md) | Mass in plant uptake (soil --> outside) | real | kg/ha |
| [rctn\_seo4, rctn\_seo3, rctn\_born](hru/rctn.md) | Mass transferred via reaction (soil --> transferred) | real | kg/ha |
| [sorb\_seo4, sorb\_seo3, sorb\_born](hru/sorb.md) | Mass transferred via sorption (soil --> sorbed mass) | real | kg/ha |
| [conc\_seo4, conc\_seo3, conc\_born](hru/conc.md) | Concentration in soil water | real | g/m3 |
| [seo4\_srbd, seo3\_srbd, born\_srbd](hru/srbd.md) | Mass sorbed in soil profile | real | kg/ha |

## Reporting differences

* The file title ends in `daily`, `monthly`, `yearly`, or `average annual`. [Titles](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L193)
* In the monthly and yearly legends, the `conc` and `srbd` lines end with `(averaged over month)` or `(averaged over year)`. In the average annual legend they end with `(averaged over years)`. [Monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L258-L259), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L299-L300), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L340-L341)
* In the average annual legend, the flux lines give the unit `kg/ha/yr`; the `conc` line gives g/m3 and the `srbd` line gives kg/ha. [Average annual legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L321-L341)
* Monthly rows divide `sl`, `conc`, and `srbd` by the days in the month. Yearly rows divide the same three groups by `time%day_end_yr`. Average annual rows divide all twenty groups by `time%nbyr`. [Monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L121-L126), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L223-L228), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L303-L324)
