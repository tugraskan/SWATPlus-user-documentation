# HRU nutrient balance

HRU nutrient balance output is written for each HRU at daily, monthly, yearly, and average annual time steps. A period is active when its `print.prt` flag `pco%nb_hru%d`, `%m`, `%y`, or `%a` is `y`. [File setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L102-L106), [data writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L72-L74)

* hru\_nb\_day.txt
* hru\_nb\_day.csv
* hru\_nb\_mon.txt
* hru\_nb\_mon.csv
* hru\_nb\_yr.txt
* hru\_nb\_yr.csv
* hru\_nb\_aa.txt
* hru\_nb\_aa.csv

A `.csv` copy is written only when `pco%csvout == "y"`. [CSV setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L108-L111), [CSV data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L75-L77)

* Each file starts with the basin name and `prog`, then the column-name row `nb_hdr`, then a units row `nb_hdr_units`. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L104-L106)
* A data row holds the time and object values, the nutrient-balance record `hnb_d(j)` (19 values), then `plant_cov` and `mgt_ops`. Each nutrient column takes the n-th value of the record in declaration order and the n-th name of the header record. [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L73-L74), [Record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L81-L103), [Header record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L360-L389)
* The units row prints `kgha` under each of the 19 nutrient columns and blanks under the others. The declaration comments give the unit as kg N/ha or kg P/ha. [Units row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L392-L419)
* The data format is `4i6,2i8,2x,a8,4f12.3,15f17.3,7x,a16,a30`. [Format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L327)

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
| [jday](hru/jday.md) | Julian day | integer | n/a |
| [mon](hru/mon.md) | Month | integer | n/a |
| [day](hru/day.md) | Day of the month | integer | n/a |
| [yr](hru/yr.md) | Calendar year | integer | n/a |
| [unit](hru/unit.md) | HRU number | integer | n/a |
| [gis\_id](hru/gis_id.md) | GIS ID of the HRU object | integer | n/a |
| [name](hru/name.md) | Name of the HRU object | string | n/a |
| [grzn](hru/grzn.md) | Total nitrogen added to soil from grazing | real | kg N/ha |
| [grzp](hru/grzp.md) | Total phosphorus added to soil from grazing | real | kg P/ha |
| [lab\_min\_p](hru/lab_min_p.md) | Phosphorus moving from the labile mineral pool to the active mineral pool | real | kg P/ha |
| [act\_sta\_p](hru/act_sta_p.md) | Phosphorus moving from the active mineral pool to the stable mineral pool | real | kg P/ha |
| [fertn](hru/fertn.md) | Total nitrogen applied to soil | real | kg N/ha |
| [fertp](hru/fertp.md) | Total phosphorus applied to soil | real | kg P/ha |
| [fixn](hru/fixn.md) | Nitrogen added to plant biomass via fixation | real | kg N/ha |
| [denit](hru/denit.md) | Nitrogen lost from the nitrate pool by denitrification | real | kg N/ha |
| [act\_nit\_n](hru/act_nit_n.md) | Nitrogen moving from the active organic pool to the nitrate pool | real | kg N/ha |
| [act\_sta\_n](hru/act_sta_n.md) | Nitrogen moving from the active organic pool to the stable pool | real | kg N/ha |
| [org\_lab\_p](hru/org_lab_p.md) | Phosphorus moving from the organic pool to the labile pool | real | kg P/ha |
| [rsd\_nitorg\_n](hru/rsd_nitorg_n.md) | Nitrogen moving from the fresh organic pool (residue) to the nitrate and active organic pools | real | kg N/ha |
| [rsd\_laborg\_p](hru/rsd_laborg_p.md) | Phosphorus moving from the fresh organic pool (residue) to the labile and organic pools | real | kg P/ha |
| [no3atmo](hru/no3atmo.md) | Nitrate added to the soil from atmospheric deposition | real | kg N/ha |
| [nh4atmo](hru/nh4atmo.md) | Ammonia added to the soil from atmospheric deposition | real | kg N/ha |
| [nuptake](hru/nuptake.md) | Plant nitrogen uptake | real | kg N/ha |
| [puptake](hru/puptake.md) | Plant phosphorus uptake | real | kg P/ha |
| [gwsoiln](hru/gwsoiln.md) | Nitrate added to the soil from the aquifer | real | kg N/ha |
| [gwsoilp](hru/gwsoilp.md) | Phosphorus added to the soil from the aquifer | real | kg P/ha |
| [plant\_cov](hru/plant_cov.md) | Plant cover label | string | n/a |
| [mgt\_ops](hru/mgt_ops.md) | Management operation label | string | n/a |

## Reporting differences

* The monthly record adds each daily record, and the yearly record adds each monthly record. [Monthly sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L41), [yearly sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L103)
* The average annual file is written once, when `time%end_sim == 1`, after the accumulated record `hnb_a(j)` is divided by `time%yrs_prt`. [Average annual write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L263-L265)
