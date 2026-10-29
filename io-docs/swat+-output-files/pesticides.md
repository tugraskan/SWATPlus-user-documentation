# Pesticides

Pesticide output is written only when pesticides are configured and the corresponding object-level print option is enabled. Daily, monthly, yearly, and average-annual reports use `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same headings. A separate row is written for each pesticide.

## HRU and landscape pesticide balance

The `hru_pest_*` and `basin_ls_pest_*` families use this schema:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](pesticides/jday-hru-and-landscape-pesticide-balance.md), [mon](pesticides/mon-hru-and-landscape-pesticide-balance.md), [day](pesticides/day-hru-and-landscape-pesticide-balance.md), [yr](pesticides/yr-hru-and-landscape-pesticide-balance.md) | Reporting date | n/a |
| [unit](pesticides/unit-hru-and-landscape-pesticide-balance.md), [gis_id](pesticides/gis_id-hru-and-landscape-pesticide-balance.md), [name](pesticides/name-hru-and-landscape-pesticide-balance.md) | Object identifiers and name | n/a |
| [pesticide](pesticides/pesticide-hru-and-landscape-pesticide-balance.md) | Pesticide name | n/a |
| [on_plant_kg/ha](pesticides/on_plant_kg-per-ha.md) | Pesticide on plant material | kg/ha |
| [soil_kg/ha](pesticides/soil_kg-per-ha.md) | Pesticide in soil | kg/ha |
| [sed_kg/ha](pesticides/sed_kg-per-ha.md) | Pesticide transported with sediment | kg/ha |
| [surq_kg/ha](pesticides/surq_kg-per-ha.md), [latq_kg/ha](pesticides/latq_kg-per-ha.md), [tileq_kg/ha](pesticides/tileq_kg-per-ha.md), [perc_kg/ha](pesticides/perc_kg-per-ha.md) | Pesticide transported by surface runoff, lateral flow, tile flow, and percolation | kg/ha |
| [apply_s_kg/ha](pesticides/apply_s_kg-per-ha.md), [apply_f_kg/ha](pesticides/apply_f_kg-per-ha.md) | Pesticide applied to soil and foliage | kg/ha |
| [decay_s_kg/ha](pesticides/decay_s_kg-per-ha.md), [decay_f_kg/ha](pesticides/decay_f_kg-per-ha.md) | Pesticide decay in soil and on foliage | kg/ha |
| [wash_kg/ha](pesticides/wash_kg-per-ha.md) | Pesticide washed from foliage | kg/ha |
| [metab_s_kg/ha](pesticides/metab_s_kg-per-ha.md), [metab_f_kg/ha](pesticides/metab_f_kg-per-ha.md) | Metabolite production in soil and on foliage | kg/ha |
| [uptake_kg/ha](pesticides/uptake_kg-per-ha.md) | Plant uptake | kg/ha |
| [in_plant_kg/ha](pesticides/in_plant_kg-per-ha.md) | Pesticide stored in plant material | kg/ha |
| [harv_export_kg/ha](pesticides/harv_export_kg-per-ha.md), [harvest_sink_kg/ha](pesticides/harvest_sink_kg-per-ha.md), [kill_ret_kg/ha](pesticides/kill_ret_kg-per-ha.md) | Harvest export, harvest sink, and plant-kill return | kg/ha |

## Channel and reservoir pesticide balance

The `channel_pest_*`, `reservoir_pest_*`, `basin_ch_pest_*`, and `basin_res_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](pesticides/jday-channel-and-reservoir-pesticide-balance.md), [mon](pesticides/mon-channel-and-reservoir-pesticide-balance.md), [day](pesticides/day-channel-and-reservoir-pesticide-balance.md), [yr](pesticides/yr-channel-and-reservoir-pesticide-balance.md), [unit](pesticides/unit-channel-and-reservoir-pesticide-balance.md), [gis_id](pesticides/gis_id-channel-and-reservoir-pesticide-balance.md), [name](pesticides/name-channel-and-reservoir-pesticide-balance.md), [pesticide](pesticides/pesticide-channel-and-reservoir-pesticide-balance.md) | Reporting date, object identity, and pesticide | n/a |
| [tot_in_kg](pesticides/tot_in_kg-channel-and-reservoir-pesticide-balance.md) | Total pesticide entering | kg |
| [sol_out_kg](pesticides/sol_out_kg.md), [sor_out_kg](pesticides/sor_out_kg.md) | Dissolved and sorbed pesticide leaving | kg |
| [react_h2o_kg](pesticides/react_h2o_kg.md), [metab_h2o_kg](pesticides/metab_h2o_kg.md) | Reaction loss and metabolite production in water | kg |
| [volat_kg](pesticides/volat_kg.md) | Volatilization loss | kg |
| [settle_kg](pesticides/settle_kg.md), [resuspend_kg](pesticides/resuspend_kg.md), [diffuse_kg](pesticides/diffuse_kg.md) | Settling, resuspension, and diffusion | kg |
| [react_benth_kg](pesticides/react_benth_kg.md), [metab_benth_kg](pesticides/metab_benth_kg.md), [bury_benth_kg](pesticides/bury_benth_kg.md) | Benthic reaction, metabolite production, and burial | kg |
| [water_stor_kg](pesticides/water_stor_kg.md), [benthic_kg](pesticides/benthic_kg.md) | Pesticide stored in water and benthic sediment | kg |

## Aquifer pesticide balance

The `aquifer_pest_*` and `basin_aqu_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](pesticides/jday-aquifer-pesticide-balance.md), [mon](pesticides/mon-aquifer-pesticide-balance.md), [day](pesticides/day-aquifer-pesticide-balance.md), [yr](pesticides/yr-aquifer-pesticide-balance.md), [unit](pesticides/unit-aquifer-pesticide-balance.md), [gis_id](pesticides/gis_id-aquifer-pesticide-balance.md), [name](pesticides/name-aquifer-pesticide-balance.md), [pesticide](pesticides/pesticide-aquifer-pesticide-balance.md) | Reporting date, object identity, and pesticide | n/a |
| [tot_in_kg](pesticides/tot_in_kg-aquifer-pesticide-balance.md) | Total pesticide entering the aquifer | kg |
| [sol_flo_kg](pesticides/sol_flo_kg.md), [sor_flo_kg](pesticides/sor_flo_kg.md) | Dissolved and sorbed pesticide leaving with groundwater flow | kg |
| [sol_perc_kg](pesticides/sol_perc_kg.md) | Dissolved pesticide entering with percolation | kg |
| [react_kg](pesticides/react_kg.md), [metab_kg](pesticides/metab_kg.md) | Reaction loss and metabolite production | kg |
| [stor_ave_kg](pesticides/stor_ave_kg.md), [stor_init_kg](pesticides/stor_init_kg.md), [stor_final_kg](pesticides/stor_final_kg.md) | Average, initial, and final pesticide storage | kg |
