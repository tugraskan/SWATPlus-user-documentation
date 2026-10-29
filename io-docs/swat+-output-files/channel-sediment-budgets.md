# Channel Sediment Budgets

SWAT+ has several channel sediment reports. They are separate schemas and should not be interpreted as variants of one table. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`, with TXT and CSV variants where enabled.

## Channel nutrient and sediment budget

The `sd_chanbud_*` and `basin_sd_chanbud_*` files use this printed schema:

| Field | Description | Unit |
| --- | --- | --- |
| [jday](channel-sediment-budgets/jday.md), [mon](channel-sediment-budgets/mon.md), [day](channel-sediment-budgets/day.md), [yr](channel-sediment-budgets/yr.md) | Reporting date | n/a |
| [unit](channel-sediment-budgets/unit.md), [gis_id](channel-sediment-budgets/gis_id.md), [name](channel-sediment-budgets/name.md) | Channel or basin identifiers | n/a |
| [in_sed](channel-sediment-budgets/in_sed.md), [out_sed](channel-sediment-budgets/out_sed.md) | Incoming and outgoing sediment | tons |
| [fp_dep](channel-sediment-budgets/fp_dep.md), [ch_dep](channel-sediment-budgets/ch_dep.md) | Floodplain and channel deposition | tons |
| [bank_ero](channel-sediment-budgets/bank_ero.md), [bed_ero](channel-sediment-budgets/bed_ero.md) | Bank and bed erosion | tons |
| [in_no3](channel-sediment-budgets/in_no3.md), [in_orgn](channel-sediment-budgets/in_orgn.md), [out_no3](channel-sediment-budgets/out_no3.md), [out_orgn](channel-sediment-budgets/out_orgn.md) | Incoming and outgoing nitrogen | kg |
| [fp_no3](channel-sediment-budgets/fp_no3.md), [bank_no3](channel-sediment-budgets/bank_no3.md), [bed_no3](channel-sediment-budgets/bed_no3.md), [fp_orgn](channel-sediment-budgets/fp_orgn.md), [ch_orgn](channel-sediment-budgets/ch_orgn.md), [bank_orgn](channel-sediment-budgets/bank_orgn.md), [bed_orgn](channel-sediment-budgets/bed_orgn.md) | Nitrogen deposition or erosion terms | kg |
| [in_solp](channel-sediment-budgets/in_solp.md), [in_orgp](channel-sediment-budgets/in_orgp.md), [out_solp](channel-sediment-budgets/out_solp.md), [out_orgp](channel-sediment-budgets/out_orgp.md) | Incoming and outgoing phosphorus | kg |
| [fp_solp](channel-sediment-budgets/fp_solp.md), [bank_solp](channel-sediment-budgets/bank_solp.md), [bed_solp](channel-sediment-budgets/bed_solp.md), [fp_orgp](channel-sediment-budgets/fp_orgp.md), [ch_orgp](channel-sediment-budgets/ch_orgp.md), [bank_orgp](channel-sediment-budgets/bank_orgp.md), [bed_orgp](channel-sediment-budgets/bed_orgp.md) | Phosphorus deposition or erosion terms | kg |
| [no3_orgn](channel-sediment-budgets/no3_orgn.md), [solp_orgp](channel-sediment-budgets/solp_orgp.md) | Combined inorganic and organic nutrient terms | kg |

## Channel erosion by channel

The `ch_sedbud_*` files report `jday`, `mon`, `day`, `yr`, `ichan`, `ob`, `name`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`.

`wid` and `dep` are channel dimensions in m; `fp_km2` is floodplain area; `ebank_t`, `ebtm_t`, and `fp_t` are mass terms in tons; and `ebank_m`, `ebtm_m`, and `fp_mm` are equivalent-depth or dimensional terms in m or mm as printed.

## Channel erosion by order

The `chanbud_order_*` files report `jday`, `mon`, `day`, `yr`, `iord`, `num`, `wid`, `dep`, `fp_km2`, `ebank_t`, `ebtm_t`, `ebank_m`, `ebtm_m`, `fp_t`, and `fp_mm`. This is the same erosion summary grouped by channel order instead of individual channel.

## Basin sediment budget

The `sedbud_*` files report `jday`, `mon`, `day`, `yr`, `upland_t`, `ebank_t`, `ebtm_t`, `fp_t`, `res_dep_t`, and `wet_dep_t`. The last six columns are basin sediment sources and sinks in tons.
