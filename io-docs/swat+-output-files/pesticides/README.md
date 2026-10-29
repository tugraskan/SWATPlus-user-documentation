# Pesticides

Pesticide output is written only when pesticides are configured and the corresponding object-level print option is enabled. Daily, monthly, yearly, and average-annual reports use `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same headings. A separate row is written for each pesticide.

## HRU and landscape pesticide balance

The `hru_pest_*` and `basin_ls_pest_*` families use this schema:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-hru-and-landscape-pesticide-balance.md), [mon](mon-hru-and-landscape-pesticide-balance.md), [day](day-hru-and-landscape-pesticide-balance.md), [yr](yr-hru-and-landscape-pesticide-balance.md) | Reporting date | n/a |
| [unit](unit-hru-and-landscape-pesticide-balance.md), [gis_id](gis_id-hru-and-landscape-pesticide-balance.md), [name](name-hru-and-landscape-pesticide-balance.md) | Object identifiers and name | n/a |
| [pesticide](pesticide-hru-and-landscape-pesticide-balance.md) | Pesticide name | n/a |
| [on_plant_kg/ha](on_plant_kg-per-ha.md) | Pesticide on plant material | kg/ha |
| [soil_kg/ha](soil_kg-per-ha.md) | Pesticide in soil | kg/ha |
| [sed_kg/ha](sed_kg-per-ha.md) | Pesticide transported with sediment | kg/ha |
| [surq_kg/ha](surq_kg-per-ha.md), [latq_kg/ha](latq_kg-per-ha.md), [tileq_kg/ha](tileq_kg-per-ha.md), [perc_kg/ha](perc_kg-per-ha.md) | Pesticide transported by surface runoff, lateral flow, tile flow, and percolation | kg/ha |
| [apply_s_kg/ha](apply_s_kg-per-ha.md), [apply_f_kg/ha](apply_f_kg-per-ha.md) | Pesticide applied to soil and foliage | kg/ha |
| [decay_s_kg/ha](decay_s_kg-per-ha.md), [decay_f_kg/ha](decay_f_kg-per-ha.md) | Pesticide decay in soil and on foliage | kg/ha |
| [wash_kg/ha](wash_kg-per-ha.md) | Pesticide washed from foliage | kg/ha |
| [metab_s_kg/ha](metab_s_kg-per-ha.md), [metab_f_kg/ha](metab_f_kg-per-ha.md) | Metabolite production in soil and on foliage | kg/ha |
| [uptake_kg/ha](uptake_kg-per-ha.md) | Plant uptake | kg/ha |
| [in_plant_kg/ha](in_plant_kg-per-ha.md) | Pesticide stored in plant material | kg/ha |
| [harv_export_kg/ha](harv_export_kg-per-ha.md), [harvest_sink_kg/ha](harvest_sink_kg-per-ha.md), [kill_ret_kg/ha](kill_ret_kg-per-ha.md) | Harvest export, harvest sink, and plant-kill return | kg/ha |

## Channel and reservoir pesticide balance

The `channel_pest_*`, `reservoir_pest_*`, `basin_ch_pest_*`, and `basin_res_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-channel-and-reservoir-pesticide-balance.md), [mon](mon-channel-and-reservoir-pesticide-balance.md), [day](day-channel-and-reservoir-pesticide-balance.md), [yr](yr-channel-and-reservoir-pesticide-balance.md), [unit](unit-channel-and-reservoir-pesticide-balance.md), [gis_id](gis_id-channel-and-reservoir-pesticide-balance.md), [name](name-channel-and-reservoir-pesticide-balance.md), [pesticide](pesticide-channel-and-reservoir-pesticide-balance.md) | Reporting date, object identity, and pesticide | n/a |
| [tot_in_kg](tot_in_kg-channel-and-reservoir-pesticide-balance.md) | Total pesticide entering | kg |
| [sol_out_kg](sol_out_kg.md), [sor_out_kg](sor_out_kg.md) | Dissolved and sorbed pesticide leaving | kg |
| [react_h2o_kg](react_h2o_kg.md), [metab_h2o_kg](metab_h2o_kg.md) | Reaction loss and metabolite production in water | kg |
| [volat_kg](volat_kg.md) | Volatilization loss | kg |
| [settle_kg](settle_kg.md), [resuspend_kg](resuspend_kg.md), [diffuse_kg](diffuse_kg.md) | Settling, resuspension, and diffusion | kg |
| [react_benth_kg](react_benth_kg.md), [metab_benth_kg](metab_benth_kg.md), [bury_benth_kg](bury_benth_kg.md) | Benthic reaction, metabolite production, and burial | kg |
| [water_stor_kg](water_stor_kg.md), [benthic_kg](benthic_kg.md) | Pesticide stored in water and benthic sediment | kg |

## Aquifer pesticide balance

The `aquifer_pest_*` and `basin_aqu_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-aquifer-pesticide-balance.md), [mon](mon-aquifer-pesticide-balance.md), [day](day-aquifer-pesticide-balance.md), [yr](yr-aquifer-pesticide-balance.md), [unit](unit-aquifer-pesticide-balance.md), [gis_id](gis_id-aquifer-pesticide-balance.md), [name](name-aquifer-pesticide-balance.md), [pesticide](pesticide-aquifer-pesticide-balance.md) | Reporting date, object identity, and pesticide | n/a |
| [tot_in_kg](tot_in_kg-aquifer-pesticide-balance.md) | Total pesticide entering the aquifer | kg |
| [sol_flo_kg](sol_flo_kg.md), [sor_flo_kg](sor_flo_kg.md) | Dissolved and sorbed pesticide leaving with groundwater flow | kg |
| [sol_perc_kg](sol_perc_kg.md) | Dissolved pesticide entering with percolation | kg |
| [react_kg](react_kg.md), [metab_kg](metab_kg.md) | Reaction loss and metabolite production | kg |
| [stor_ave_kg](stor_ave_kg.md), [stor_init_kg](stor_init_kg.md), [stor_final_kg](stor_final_kg.md) | Average, initial, and final pesticide storage | kg |
