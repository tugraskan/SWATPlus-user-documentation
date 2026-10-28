# Channel Sediment Budgets

SWAT+ has several channel sediment reports. They are separate schemas and should not be interpreted as variants of one table. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`, with TXT and CSV variants where enabled.

## Channel nutrient and sediment budget

The `sd_chanbud_*` and `basin_sd_chanbud_*` files use this printed schema:

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr | Reporting date | n/a |
| unit, gis_id, name | Channel or basin identifiers | n/a |
| in_sed, out_sed | Incoming and outgoing sediment | tons |
| fp_dep, ch_dep | Floodplain and channel deposition | tons |
| bank_ero, bed_ero | Bank and bed erosion | tons |
| in_no3, in_orgn, out_no3, out_orgn | Incoming and outgoing nitrogen | kg |
| fp_no3, bank_no3, bed_no3, fp_orgn, ch_orgn, bank_orgn, bed_orgn | Nitrogen deposition or erosion terms | kg |
| in_solp, in_orgp, out_solp, out_orgp | Incoming and outgoing phosphorus | kg |
| fp_solp, bank_solp, bed_solp, fp_orgp, ch_orgp, bank_orgp, bed_orgp | Phosphorus deposition or erosion terms | kg |
| no3_orgn, solp_orgp | Combined inorganic and organic nutrient terms | kg |

## Channel erosion by channel

The `ch_sedbud_*` files report `jday`, `mon`, `day`, `yr`, `ichan`, `ob`, `name`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`.

`wid` and `dep` are channel dimensions in m; `fp_km2` is floodplain area; `ebank_t`, `ebtm_t`, and `fp_t` are mass terms in tons; and `ebank_m`, `ebtm_m`, and `fp_mm` are equivalent-depth or dimensional terms in m or mm as printed.

## Channel erosion by order

The `chanbud_order_*` files report `jday`, `mon`, `day`, `yr`, `iord`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`. This is the same erosion summary grouped by channel order instead of individual channel.

## Basin sediment budget

The `sedbud_*` files report `jday`, `mon`, `day`, `yr`, `upland_t`, `ebank_t`, `ebtm_t`, `fp_t`, `res_dep_t`, and `wet_dep_t`. The last six columns are basin sediment sources and sinks in tons.
