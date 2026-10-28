# Pesticides

Pesticide output is written only when pesticides are configured and the corresponding object-level print option is enabled. Daily, monthly, yearly, and average-annual reports use `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same headings. A separate row is written for each pesticide.

## HRU and landscape pesticide balance

The `hru_pest_*` and `basin_ls_pest_*` families use this schema:

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr | Reporting date | n/a |
| unit, gis_id, name | Object identifiers and name | n/a |
| pesticide | Pesticide name | n/a |
| on_plant_kg/ha | Pesticide on plant material | kg/ha |
| soil_kg/ha | Pesticide in soil | kg/ha |
| sed_kg/ha | Pesticide transported with sediment | kg/ha |
| surq_kg/ha, latq_kg/ha, tileq_kg/ha, perc_kg/ha | Pesticide transported by surface runoff, lateral flow, tile flow, and percolation | kg/ha |
| apply_s_kg/ha, apply_f_kg/ha | Pesticide applied to soil and foliage | kg/ha |
| decay_s_kg/ha, decay_f_kg/ha | Pesticide decay in soil and on foliage | kg/ha |
| wash_kg/ha | Pesticide washed from foliage | kg/ha |
| metab_s_kg/ha, metab_f_kg/ha | Metabolite production in soil and on foliage | kg/ha |
| uptake_kg/ha | Plant uptake | kg/ha |
| in_plant_kg/ha | Pesticide stored in plant material | kg/ha |
| harv_export_kg/ha, harvest_sink_kg/ha, kill_ret_kg/ha | Harvest export, harvest sink, and plant-kill return | kg/ha |

## Channel and reservoir pesticide balance

The `channel_pest_*`, `reservoir_pest_*`, `basin_ch_pest_*`, and `basin_res_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr, unit, gis_id, name, pesticide | Reporting date, object identity, and pesticide | n/a |
| tot_in_kg | Total pesticide entering | kg |
| sol_out_kg, sor_out_kg | Dissolved and sorbed pesticide leaving | kg |
| react_h2o_kg, metab_h2o_kg | Reaction loss and metabolite production in water | kg |
| volat_kg | Volatilization loss | kg |
| settle_kg, resuspend_kg, diffuse_kg | Settling, resuspension, and diffusion | kg |
| react_benth_kg, metab_benth_kg, bury_benth_kg | Benthic reaction, metabolite production, and burial | kg |
| water_stor_kg, benthic_kg | Pesticide stored in water and benthic sediment | kg |

## Aquifer pesticide balance

The `aquifer_pest_*` and `basin_aqu_pest_*` families share these headings:

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr, unit, gis_id, name, pesticide | Reporting date, object identity, and pesticide | n/a |
| tot_in_kg | Total pesticide entering the aquifer | kg |
| sol_flo_kg, sor_flo_kg | Dissolved and sorbed pesticide leaving with groundwater flow | kg |
| sol_perc_kg | Dissolved pesticide entering with percolation | kg |
| react_kg, metab_kg | Reaction loss and metabolite production | kg |
| stor_ave_kg, stor_init_kg, stor_final_kg | Average, initial, and final pesticide storage | kg |
