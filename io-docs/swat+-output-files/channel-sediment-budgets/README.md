# Channel Sediment Budgets

SWAT+ has several channel sediment reports. They are separate schemas and should not be interpreted as variants of one table. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`, with TXT and CSV variants where enabled.

## Channel nutrient and sediment budget

The `sd_chanbud_*` and `basin_sd_chanbud_*` files use this printed schema:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md), [mon](mon.md), [day](day.md), [yr](yr.md) | Reporting date | n/a |
| [unit](unit.md), [gis_id](gis_id.md), [name](name.md) | Channel or basin identifiers | n/a |
| [in_sed](in_sed.md), [out_sed](out_sed.md) | Incoming and outgoing sediment | tons |
| [fp_dep](fp_dep.md), [ch_dep](ch_dep.md) | Floodplain and channel deposition | tons |
| [bank_ero](bank_ero.md), [bed_ero](bed_ero.md) | Bank and bed erosion | tons |
| [in_no3](in_no3.md), [in_orgn](in_orgn.md), [out_no3](out_no3.md), [out_orgn](out_orgn.md) | Incoming and outgoing nitrogen | kg |
| [fp_no3](fp_no3.md), [bank_no3](bank_no3.md), [bed_no3](bed_no3.md), [fp_orgn](fp_orgn.md), [ch_orgn](ch_orgn.md), [bank_orgn](bank_orgn.md), [bed_orgn](bed_orgn.md) | Nitrogen deposition or erosion terms | kg |
| [in_solp](in_solp.md), [in_orgp](in_orgp.md), [out_solp](out_solp.md), [out_orgp](out_orgp.md) | Incoming and outgoing phosphorus | kg |
| [fp_solp](fp_solp.md), [bank_solp](bank_solp.md), [bed_solp](bed_solp.md), [fp_orgp](fp_orgp.md), [ch_orgp](ch_orgp.md), [bank_orgp](bank_orgp.md), [bed_orgp](bed_orgp.md) | Phosphorus deposition or erosion terms | kg |
| [no3_orgn](no3_orgn.md), [solp_orgp](solp_orgp.md) | Combined inorganic and organic nutrient terms | kg |

## Channel erosion by channel

The `ch_sedbud_*` files report `jday`, `mon`, `day`, `yr`, `ichan`, `ob`, `name`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`.

`wid` and `dep` are channel dimensions in m; `fp_km2` is floodplain area; `ebank_t`, `ebtm_t`, and `fp_t` are mass terms in tons; and `ebank_m`, `ebtm_m`, and `fp_mm` are equivalent-depth or dimensional terms in m or mm as printed.

## Channel erosion by order

The `chanbud_order_*` files report `jday`, `mon`, `day`, `yr`, `iord`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`. This is the same erosion summary grouped by channel order instead of individual channel.

## Basin sediment budget

The `sedbud_*` files report `jday`, `mon`, `day`, `yr`, `upland_t`, `ebank_t`, `ebtm_t`, `fp_t`, `res_dep_t`, and `wet_dep_t`. The last six columns are basin sediment sources and sinks in tons.
