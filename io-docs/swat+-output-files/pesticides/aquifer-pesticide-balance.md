# Aquifer pesticide balance

All 16 daily, monthly, yearly, and average-annual TXT and CSV variants of `aquifer_pest_*` and `basin_aqu_pest_*` share 17 headings and 17 data values. Each file starts with a title and headings. Units are in the mass headings. Enable the relevant period on the shared [`pest` print row](README.md#how-to-produce-these-files), and set `csvout = y` for CSV. The openers require an aquifer and a positive total constituent count. Rows are written per configured pesticide after the skipped years, and daily rows follow the daily print window and interval. [Basin and individual openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_pest.f90#L207), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L562), [Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_output.f90#L25)

The basin writer sums aquifer records for each pesticide. It prints `1` for both `unit` and `gis_id`, and uses the first aquifer object's name in the `name` column. [Basin sum and identifiers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aqu_pest_output.f90#L22)

## Daily 1-D aquifer values

- **Scope and initialization.** The aquifer command runs the daily producer only when the object's `dfn_tot` is zero. The writers still iterate over the aquifer objects. When initialization matches a pesticide record, it looks up the initialization name and bottom depth using the aquifer object index in the parameter table. The lookup can select a different record if the aquifer object index differs from its parameter index. The initialization formula is annotated kg/ha, and the daily balance uses the resulting number in its kg record without multiplying by aquifer area. [1-D dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L300-L303), [Writer loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L559-L570), [Initial pesticide mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L71-L94), [Daily input and record units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L306-L318), [Daily mass fields](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L369-L377).
- **Mixing and exports.** After the water budget, the routine divides stored pesticide mass by the sum of remaining water storage times `pestgwfact`, return-flow depth, revap depth, and seepage depth. It uses the same concentration for return flow and seepage and scales down both masses together if their sum exceeds available pesticide. The return-flow mass becomes `sol_flo_kg` and the seepage mass becomes `sol_perc_kg`. Both go into their respective outgoing hydrographs. Revap affects the denominator and has no pesticide export. The model assumes all routed pesticide is soluble and writes zero to `sor_flo_kg`. [Water budget](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L98-L136), [Mixing, export, and caps](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L339-L377).
- **Reaction and storage timing.** The routine records opening mass before adding routed recharge and applies decay to the combined mass. With temperature-adjusted decay enabled, it passes the local `temp_aqu` value, which stays at its initialized 0 °C. The two daily ending fields, `stor_ave_kg` and `stor_final_kg`, store the same snapshot after export for that pesticide's turn in the loop. [Temperature proxy declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L55-L59), [Opening mass, recharge, and reaction](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L306-L326), [Storage snapshot](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L366-L377).
- **Metabolite order.** The routine clears the current pesticide's `metab_kg` slot at the start of its turn. If a parent is processed before its daughter pesticide, the daughter can include that new mass in its opening storage and can then clear the earlier formation from its diagnostic. If the parent runs after its daughter, the new mass reaches live storage after the daughter's ending snapshot was recorded. The basin sums inherit these timing differences. [Pesticide loop and daughter updates](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L306-L336), [Ending snapshot](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L369-L378), [Daily basin sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aqu_pest_output.f90#L25-L34).

## Reporting periods

| Fields | Monthly and yearly | Average annual |
| --- | --- | --- |
| Input, export, reaction, and metabolite masses | Period totals | Sum of yearly masses divided by `time%yrs_prt` |
| `stor_ave_kg` | Sum of daily ending masses divided by calendar month length or `time%day_end_yr` | Sum of daily ending masses divided by `time%days_prt` |
| `stor_init_kg` | Carried from the previous period's ending mass after each reset. The first period uses the initialized value. | Uses the value initialized at the start of reporting |
| `stor_final_kg` | Daily ending mass on the reporting date | Daily ending mass on the final reporting date |

The individual and basin writers transfer monthly sums only at calendar month end. A final partial month is omitted from yearly and average-annual process sums and from the numerator of `stor_ave_kg`. The day divisors still include those days, and `stor_final_kg` still shows the last simulated day's storage. [Individual accumulation and final storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_output.f90#L44-L92), [basin accumulation and final storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aqu_pest_output.f90#L53-L101).

For the first basin monthly and yearly rows and the average-annual row, the opening mass retains only the last aquifer's initial value. The initializer resets the basin opening mass inside the aquifer loop. The daily basin writer recomputes opening mass across all aquifers. [Initialization caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L152), [Basin initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pest_output_init.f90#L12), [Basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aqu_pest_output.f90#L26), [Period operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L102)

## Columns

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-aquifer-pesticide-balance.md) | Day of year | n/a |
| [mon](mon-aquifer-pesticide-balance.md) | Month | n/a |
| [day](day-aquifer-pesticide-balance.md) | Day of month | n/a |
| [yr](yr-aquifer-pesticide-balance.md) | Calendar year | n/a |
| [unit](unit-aquifer-pesticide-balance.md) | Aquifer index or basin placeholder `1` | n/a |
| [gis_id](gis_id-aquifer-pesticide-balance.md) | Aquifer GIS ID or basin placeholder `1` | n/a |
| [name](name-aquifer-pesticide-balance.md) | Aquifer name. The basin row uses the first aquifer's name. | n/a |
| [pesticide](pesticide-aquifer-pesticide-balance.md) | Pesticide identifier | n/a |
| [tot_in_kg](tot_in_kg-aquifer-pesticide-balance.md) | Total pesticide entering the aquifer | kg |
| [sol_flo_kg](sol_flo_kg.md) | Dissolved pesticide leaving with groundwater flow | kg |
| [sor_flo_kg](sor_flo_kg.md) | Sorbed pesticide leaving with groundwater flow | kg |
| [sol_perc_kg](sol_perc_kg.md) | Dissolved pesticide exported with aquifer seepage | kg |
| [react_kg](react_kg.md) | Pesticide reaction loss | kg |
| [metab_kg](metab_kg.md) | Metabolite production | kg |
| [stor_ave_kg](stor_ave_kg.md) | Daily after-export snapshot, averaged across days in longer periods | kg |
| [stor_init_kg](stor_init_kg.md) | Storage before the pesticide's routed recharge is added | kg |
| [stor_final_kg](stor_final_kg.md) | Storage after export for that pesticide's turn in the loop | kg |

[Back to the Pesticides index](README.md).
