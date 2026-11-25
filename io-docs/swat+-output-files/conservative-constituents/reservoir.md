# Reservoir constituent fluxes and state variables

Reservoir constituent output is written for each reservoir at daily, monthly, yearly, and average annual time steps. A period is active when the model has reservoirs (`sp_ob%res > 0`), `cs_db%num_cs > 0`, and the `print.prt` flag `pco%cs_res%d`, `%m`, `%y`, or `%a` is `y`. [Daily file setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L597-L626), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L630-L631), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L663-L664), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L696-L697), [data writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L43-L245)

* reservoir\_cs\_day.txt
* reservoir\_cs\_day.csv
* reservoir\_cs\_mon.txt
* reservoir\_cs\_mon.csv
* reservoir\_cs\_yr.txt
* reservoir\_cs\_yr.csv
* reservoir\_cs\_aa.txt
* reservoir\_cs\_aa.csv

A `.csv` copy is written only when `pco%csvout == "y"`. [CSV condition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L621-L625)

* Each file starts with the basin name and `prog`, a title line, a definitions list, and one column-name row. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L600-L620)
* Every data row begins with six values: `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Then it holds eleven groups of values in the table order below, each with one value per constituent (`cs_db%num_cs` values), and ends with one `vol_m3` value. [Data row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L44-L56)
* The column-name row is the fixed header record `rescs_hdr`. It names three constituent columns for each group: `seo4`, `seo3`, and `born`. The `irr` group appears in the header as `seo4_irrg`, `seo3_irrg`, and `born_irrg`. [Header record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L57-L98)

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
| [jday](reservoir/jday.md) | Julian day | integer | n/a |
| [mon](reservoir/mon.md) | Month | integer | n/a |
| [day](reservoir/day.md) | Day of the month | integer | n/a |
| [yr](reservoir/yr.md) | Calendar year | integer | n/a |
| [unit](reservoir/unit.md) | Reservoir number | integer | n/a |
| [gis\_id](reservoir/gis_id.md) | GIS ID of the reservoir | integer | n/a |
| [seo4\_in, seo3\_in, born\_in](reservoir/in.md) | Mass entering reservoir with inflow | real | kg |
| [seo4\_out, seo3\_out, born\_out](reservoir/out.md) | Mass leaving reservoir with outflow | real | kg |
| [seo4\_seep, seo3\_seep, born\_seep](reservoir/seep.md) | Mass leaving reservoir via seepage | real | kg |
| [seo4\_setl, seo3\_setl, born\_setl](reservoir/setl.md) | Mass settling to bottom of reservoir | real | kg |
| [seo4\_rctn, seo3\_rctn, born\_rctn](reservoir/rctn.md) | Mass consumed due to chemical reaction | real | kg |
| [seo4\_prod, seo3\_prod, born\_prod](reservoir/prod.md) | Mass produced due to chemical reaction | real | kg |
| [seo4\_fert, seo3\_fert, born\_fert](reservoir/fert.md) | Mass added to reservoir via fertilizer | real | kg |
| [seo4\_irrg, seo3\_irrg, born\_irrg](reservoir/irr.md) | Mass removed from reservoir for irrigation | real | kg |
| [seo4\_div, seo3\_div, born\_div](reservoir/div.md) | Mass removed (-) or added (+) via diversion | real | kg |
| [seo4\_mass, seo3\_mass, born\_mass](reservoir/mass.md) | Mass stored in reservoir | real | kg |
| [seo4\_conc, seo3\_conc, born\_conc](reservoir/conc.md) | Concentration in reservoir water | real | g/m3 |
| [vol\_m3](reservoir/vol_m3.md) | Volume of water stored in reservoir | real | m3 |

## Reporting differences

* The file title ends in `daily`, `monthly`, `yearly`, or `average annual`. [Titles](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L602)
* In the monthly and yearly legends, the `mass`, `conc`, and `vol_m3` lines end with `(averaged over month)` or `(averaged over year)`. In the average annual legend they end with `(averaged over years)`. [Monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L649-L651), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L682-L684), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L715-L717)
* In the average annual legend, the nine flux lines `in` to `div` give the unit `kg/yr`. [Average annual legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L706-L714)
* Monthly rows divide `mass`, `conc`, and `vol_m3` by the days in the month. Yearly rows divide the same values by `time%day_end_yr`. Average annual rows divide every group and `vol_m3` by `time%nbyr`. [Monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L91-L96), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L161-L166), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L215-L230)
