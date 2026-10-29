# Channel Sediment Budgets

SWAT+ has several channel sediment reports. They are separate schemas and should not be interpreted as variants of one table. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`, with TXT and CSV variants where enabled.

## Channel nutrient and sediment budget

The `sd_chanbud_*` and `basin_sd_chanbud_*` files use this printed schema:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Object identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | Object name | n/a |
| [in_sed](in_sed.md) | Incoming sediment | tons |
| [out_sed](out_sed.md) | Outgoing sediment | tons |
| [fp_dep](fp_dep.md) | Floodplain sediment deposition | tons |
| [ch_dep](ch_dep.md) | Channel sediment deposition | tons |
| [bank_ero](bank_ero.md) | Bank erosion | tons |
| [bed_ero](bed_ero.md) | Bed erosion | tons |
| [in_no3](in_no3.md) | Incoming nitrate nitrogen | kg |
| [in_orgn](in_orgn.md) | Incoming organic nitrogen | kg |
| [out_no3](out_no3.md) | Outgoing nitrate nitrogen | kg |
| [out_orgn](out_orgn.md) | Outgoing organic nitrogen | kg |
| [fp_no3](fp_no3.md) | Floodplain deposition of nitrate nitrogen | kg |
| [bank_no3](bank_no3.md) | Bank erosion of nitrate nitrogen | kg |
| [bed_no3](bed_no3.md) | Bed erosion of nitrate nitrogen | kg |
| [fp_orgn](fp_orgn.md) | Floodplain deposition of organic nitrogen | kg |
| [ch_orgn](ch_orgn.md) | Channel deposition of organic nitrogen | kg |
| [bank_orgn](bank_orgn.md) | Bank erosion of organic nitrogen | kg |
| [bed_orgn](bed_orgn.md) | Bed erosion of organic nitrogen | kg |
| [in_solp](in_solp.md) | Incoming soluble phosphorus | kg |
| [in_orgp](in_orgp.md) | Incoming organic phosphorus | kg |
| [out_solp](out_solp.md) | Outgoing soluble phosphorus | kg |
| [out_orgp](out_orgp.md) | Outgoing organic phosphorus | kg |
| [fp_solp](fp_solp.md) | Floodplain deposition of soluble phosphorus | kg |
| [bank_solp](bank_solp.md) | Bank erosion of soluble phosphorus | kg |
| [bed_solp](bed_solp.md) | Bed erosion of soluble phosphorus | kg |
| [fp_orgp](fp_orgp.md) | Floodplain deposition of organic phosphorus | kg |
| [ch_orgp](ch_orgp.md) | Channel deposition of organic phosphorus | kg |
| [bank_orgp](bank_orgp.md) | Bank erosion of organic phosphorus | kg |
| [bed_orgp](bed_orgp.md) | Bed erosion of organic phosphorus | kg |
| [no3_orgn](no3_orgn.md) | Combined nitrate and organic nitrogen term | kg |
| [solp_orgp](solp_orgp.md) | Combined soluble and organic phosphorus term | kg |

## Channel erosion by channel

The `ch_sedbud_*` files report `jday`, `mon`, `day`, `yr`, `ichan`, `ob`, `name`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`.

`wid` and `dep` are channel dimensions in m; `fp_km2` is floodplain area; `ebank_t`, `ebtm_t`, and `fp_t` are mass terms in tons; and `ebank_m`, `ebtm_m`, and `fp_mm` are equivalent-depth or dimensional terms in m or mm as printed.

## Channel erosion by order

The `chanbud_order_*` files report `jday`, `mon`, `day`, `yr`, `iord`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`. This is the same erosion summary grouped by channel order instead of individual channel.

## Basin sediment budget

The `sedbud_*` files report `jday`, `mon`, `day`, `yr`, `upland_t`, `ebank_t`, `ebtm_t`, `fp_t`, `res_dep_t`, and `wet_dep_t`. The last six columns are basin sediment sources and sinks in tons.
