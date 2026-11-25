# HRU and landscape pesticide balance

The `hru_pest_*` and `basin_ls_pest_*` files share 27 columns across daily, monthly, yearly, and average-annual TXT and CSV. Enable the desired periods on the [shared pesticide print row](README.md#how-to-produce-these-files). The files have a title and headings. Daily rows follow the daily print window and interval. [HRU opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_pest.f90#L15), [Basin opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_pest.f90#L462), [HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pesticide_output.f90#L28)

## Basin landscape values

The basin writer uses the first HRU's name and prints `1` in both identifier columns. It loops over the first `sp_ob%hru` landscape-element entries and uses each entry's object number as an HRU index without checking its object type. It reads a basin-area fraction but adds each selected HRU record without applying that fraction. The resulting numbers are unweighted sums of HRU values even though the headings still say `kg/ha`. Where two elements select the same HRU, its record contributes twice. [Basin mapping and sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_ls_pest_output.f90#L22-L33).

## Daily records and routing

- **Applications and storage.** The two application fields accumulate all calls to `pest_apply` for that HRU and pesticide on the day. The routine apportions the application between soil and foliage, and adds the soil portion to the first two layers. The final daily soil diagnostic sums all layers. The foliage and internal plant diagnostics are overwritten for each plant, leaving the last plant's values. With no plant iterations those two diagnostics retain their previous values because the daily reset preserves storage fields. [Application split](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_apply.f90#L31-L60), [Daily reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L162-L167), [Storage preserved by multiplication](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L122-L145), [Storage producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_soil_tot.f90#L23-L32).
- **Wash-off, decay, and metabolites.** Wash-off transfers pesticide from each qualifying plant into surface soil, while `wash` keeps only the last qualifying plant's amount. Soil decay sums the losses across layers and foliage decay sums across plants. Metabolite production is added under the daughter pesticide's row, using the compartment-specific yield and the daughter-to-parent molecular-weight ratio. A daughter processed later in the same routine can decay material that was just formed. [Wash-off assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_washp.f90#L26-L39), [Soil decay and daughters](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L38-L69), [Foliage decay and daughters](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L71-L98).
- **Root uptake and harvest.** Uptake sums the mass removed from the soil across the plants and layers processed by the routine. A pesticide configured as a terminal plant sink still counts in `uptake`, but that mass does not enter the internal plant pool and leaves the separate `harvest_sink` output slot at zero. Biomass, grain, and tuber harvests contribute to `harv_export`. The `kill_ret` diagnostic records internal pesticide returned with biomass clippings or at tuber harvest. The ordinary plant-kill routine returns pesticide from foliage and internal storage to surface soil without updating `kill_ret`. [Uptake and sink](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L101-L115), [Biomass harvest](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L58-L100), [Grain harvest](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvgrain.f90#L65-L78), [Tuber harvest](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvtuber.f90#L69-L96), [Plant kill](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_killop.f90#L58-L64).
- **Transport and outgoing loads.** `pest_lch` removes dissolved pesticide in surface runoff from layer 1, tile flow from the drain layer, and lateral flow from each layer. It reports only the amount leaving the last layer in `perc`. The sediment calculation runs separately under the runoff and erosion conditions, and filter strips and grassed waterways can reduce the reported surface and sediment amounts before routing. The outgoing surface hydrograph combines `surq + sed`, and the lateral, tile, and recharge hydrographs each use their matching diagnostic multiplied by HRU area. Total surface, lateral, and tile outflow excludes the separate recharge load. [Dissolved transport](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_lch.f90#L59-L95), [Sediment call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L521-L528), [Filter strip](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_filter.f90#L232-L245), [Grassed waterway](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_grass_wway.f90#L225-L240), [Component and total hydrographs](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L89-L174).

## Reporting periods

Both writers transfer monthly values only at calendar month end. A final partial month is omitted from yearly and average-annual process sums and from the numerators of the storage means. The day divisors still include those days. [HRU month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pesticide_output.f90#L47-L49), [basin month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_ls_pest_output.f90#L53-L55).

| Fields | Monthly and yearly | Average annual |
| --- | --- | --- |
| `on_plant_kg/ha`, `soil_kg/ha`, `in_plant_kg/ha` | Sums of daily storage values divided by calendar month length or `time%day_end_yr` | Accumulated storage values divided by `time%days_prt` |
| `harv_export_kg/`, `harvest_sink_kg`, `kill_ret_kg/ha` | Sums of daily amounts divided by the same day counts | Accumulated amounts divided by both `time%yrs_prt` and `time%days_prt` |
| All other flux and process fields | Period totals | Accumulated amounts divided by `time%yrs_prt` |

The individual HRU yearly accumulator is reset in time control. The basin yearly accumulator is divided for output in place, and the source has no matching yearly reset for it. Later basin yearly and average-annual results can therefore include values from earlier years. [HRU period writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pesticide_output.f90#L47), [Basin period writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_ls_pest_output.f90#L53), [HRU yearly reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L332), [Division operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L149)

## Columns

The two harvest headings are declared as 15-character strings. The source truncates the intended `harv_export_kg/ha` and `harvest_sink_kg/ha` headings to the labels shown below. The underlying fields are declared in kg/ha. [Heading declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L73)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-hru-and-landscape-pesticide-balance.md) | Day of year | n/a |
| [mon](mon-hru-and-landscape-pesticide-balance.md) | Month | n/a |
| [day](day-hru-and-landscape-pesticide-balance.md) | Day of month | n/a |
| [yr](yr-hru-and-landscape-pesticide-balance.md) | Calendar year | n/a |
| [unit](unit-hru-and-landscape-pesticide-balance.md) | HRU index or basin placeholder `1` | n/a |
| [gis_id](gis_id-hru-and-landscape-pesticide-balance.md) | HRU GIS identifier or basin placeholder `1` | n/a |
| [name](name-hru-and-landscape-pesticide-balance.md) | HRU name. Basin rows use the first HRU's name. | n/a |
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
| [wash_kg/ha](wash_kg-per-ha.md) | Pesticide washed from the last qualifying plant | kg/ha |
| [metab_s_kg/ha](metab_s_kg-per-ha.md) | Metabolite produced in soil, reported on the daughter row | kg/ha |
| [metab_f_kg/ha](metab_f_kg-per-ha.md) | Metabolite produced on foliage, reported on the daughter row | kg/ha |
| [uptake_kg/ha](uptake_kg-per-ha.md) | Uptake from soil, including mass removed by the terminal sink option | kg/ha |
| [in_plant_kg/ha](in_plant_kg-per-ha.md) | Pesticide stored in plant material | kg/ha |
| [harv_export_kg/](harv_export_kg-per-ha.md) | Pesticide exported at harvest | kg/ha |
| [harvest_sink_kg](harvest_sink_kg-per-ha.md) | Harvest sink slot. The inspected source has no direct daily assignment to it. | kg/ha |
| [kill_ret_kg/ha](kill_ret_kg-per-ha.md) | Internal pesticide returned to soil by the biomass and tuber harvest routines | kg/ha |

[Back to the Pesticides index](README.md).
