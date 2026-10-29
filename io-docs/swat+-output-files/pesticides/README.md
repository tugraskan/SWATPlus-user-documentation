# Pesticides

Pesticide output is written only when pesticides are configured and the corresponding object-level print option is enabled. Daily, monthly, yearly, and average-annual reports use `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same headings. A separate row is written for each pesticide.

## HRU and landscape pesticide balance

The `hru_pest_*` and `basin_ls_pest_*` families use this schema:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-hru-and-landscape-pesticide-balance.md) | Day of year | n/a |
| [mon](mon-hru-and-landscape-pesticide-balance.md) | Month | n/a |
| [day](day-hru-and-landscape-pesticide-balance.md) | Day of month | n/a |
| [yr](yr-hru-and-landscape-pesticide-balance.md) | Calendar year | n/a |
| [unit](unit-hru-and-landscape-pesticide-balance.md) | Object identifier | n/a |
| [gis_id](gis_id-hru-and-landscape-pesticide-balance.md) | GIS identifier | n/a |
| [name](name-hru-and-landscape-pesticide-balance.md) | Object name | n/a |
| [pesticide](pesticide-hru-and-landscape-pesticide-balance.md) | Pesticide name | n/a |
| [on_plant_kg/ha](on_plant_kg-per-ha.md) | Pesticide on plant material | kg/ha |
| [soil_kg/ha](soil_kg-per-ha.md) | Pesticide in soil | kg/ha |
| [sed_kg/ha](sed_kg-per-ha.md) | Pesticide transported with sediment | kg/ha |
| [surq_kg/ha](surq_kg-per-ha.md) | Pesticide transported by surface runoff | kg/ha |
| [latq_kg/ha](latq_kg-per-ha.md) | Pesticide transported by lateral flow | kg/ha |
| [tileq_kg/ha](tileq_kg-per-ha.md) | Pesticide transported by tile flow | kg/ha |
| [perc_kg/ha](perc_kg-per-ha.md) | Pesticide transported by percolation | kg/ha |
| [apply_s_kg/ha](apply_s_kg-per-ha.md) | Pesticide applied to soil | kg/ha |
| [apply_f_kg/ha](apply_f_kg-per-ha.md) | Pesticide applied to foliage | kg/ha |
| [decay_s_kg/ha](decay_s_kg-per-ha.md) | Pesticide decay in soil | kg/ha |
| [decay_f_kg/ha](decay_f_kg-per-ha.md) | Pesticide decay on foliage | kg/ha |
| [wash_kg/ha](wash_kg-per-ha.md) | Pesticide washed from foliage | kg/ha |
| [metab_s_kg/ha](metab_s_kg-per-ha.md) | Metabolite production in soil | kg/ha |
| [metab_f_kg/ha](metab_f_kg-per-ha.md) | Metabolite production on foliage | kg/ha |
| [uptake_kg/ha](uptake_kg-per-ha.md) | Plant uptake | kg/ha |
| [in_plant_kg/ha](in_plant_kg-per-ha.md) | Pesticide stored in plant material | kg/ha |
| [harv_export_kg/ha](harv_export_kg-per-ha.md) | Pesticide exported at harvest | kg/ha |
| [harvest_sink_kg/ha](harvest_sink_kg-per-ha.md) | Pesticide harvest sink | kg/ha |
| [kill_ret_kg/ha](kill_ret_kg-per-ha.md) | Pesticide returned at plant kill | kg/ha |

## Channel and reservoir pesticide balance

The `channel_pest_*`, `reservoir_pest_*`, `basin_ch_pest_*`, and `basin_res_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-channel-and-reservoir-pesticide-balance.md) | Day of year | n/a |
| [mon](mon-channel-and-reservoir-pesticide-balance.md) | Month | n/a |
| [day](day-channel-and-reservoir-pesticide-balance.md) | Day of month | n/a |
| [yr](yr-channel-and-reservoir-pesticide-balance.md) | Calendar year | n/a |
| [unit](unit-channel-and-reservoir-pesticide-balance.md) | Object identifier | n/a |
| [gis_id](gis_id-channel-and-reservoir-pesticide-balance.md) | GIS identifier | n/a |
| [name](name-channel-and-reservoir-pesticide-balance.md) | Object name | n/a |
| [pesticide](pesticide-channel-and-reservoir-pesticide-balance.md) | Pesticide identifier | n/a |
| [tot_in_kg](tot_in_kg-channel-and-reservoir-pesticide-balance.md) | Total pesticide entering | kg |
| [sol_out_kg](sol_out_kg.md) | Dissolved pesticide leaving | kg |
| [sor_out_kg](sor_out_kg.md) | Sorbed pesticide leaving | kg |
| [react_h2o_kg](react_h2o_kg.md) | Pesticide reaction loss in water | kg |
| [metab_h2o_kg](metab_h2o_kg.md) | Metabolite production in water | kg |
| [volat_kg](volat_kg.md) | Volatilization loss | kg |
| [settle_kg](settle_kg.md) | Pesticide settling | kg |
| [resuspend_kg](resuspend_kg.md) | Pesticide resuspension | kg |
| [diffuse_kg](diffuse_kg.md) | Pesticide diffusion | kg |
| [react_benth_kg](react_benth_kg.md) | Pesticide reaction loss in benthic sediment | kg |
| [metab_benth_kg](metab_benth_kg.md) | Metabolite production in benthic sediment | kg |
| [bury_benth_kg](bury_benth_kg.md) | Pesticide burial in benthic sediment | kg |
| [water_stor_kg](water_stor_kg.md) | Pesticide stored in water | kg |
| [benthic_kg](benthic_kg.md) | Pesticide stored in benthic sediment | kg |

## Aquifer pesticide balance

The `aquifer_pest_*` and `basin_aqu_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-aquifer-pesticide-balance.md) | Day of year | n/a |
| [mon](mon-aquifer-pesticide-balance.md) | Month | n/a |
| [day](day-aquifer-pesticide-balance.md) | Day of month | n/a |
| [yr](yr-aquifer-pesticide-balance.md) | Calendar year | n/a |
| [unit](unit-aquifer-pesticide-balance.md) | Object identifier | n/a |
| [gis_id](gis_id-aquifer-pesticide-balance.md) | GIS identifier | n/a |
| [name](name-aquifer-pesticide-balance.md) | Object name | n/a |
| [pesticide](pesticide-aquifer-pesticide-balance.md) | Pesticide identifier | n/a |
| [tot_in_kg](tot_in_kg-aquifer-pesticide-balance.md) | Total pesticide entering the aquifer | kg |
| [sol_flo_kg](sol_flo_kg.md) | Dissolved pesticide leaving with groundwater flow | kg |
| [sor_flo_kg](sor_flo_kg.md) | Sorbed pesticide leaving with groundwater flow | kg |
| [sol_perc_kg](sol_perc_kg.md) | Dissolved pesticide entering with percolation | kg |
| [react_kg](react_kg.md) | Pesticide reaction loss | kg |
| [metab_kg](metab_kg.md) | Metabolite production | kg |
| [stor_ave_kg](stor_ave_kg.md) | Average pesticide storage | kg |
| [stor_init_kg](stor_init_kg.md) | Initial pesticide storage | kg |
| [stor_final_kg](stor_final_kg.md) | Final pesticide storage | kg |
