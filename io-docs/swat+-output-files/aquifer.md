# Aquifer

Aquifer outputs describe groundwater storage, water-table depth, water exchanges, and nutrient transport. Output frequency is selected in `print.prt`; individual aquifer and basin-average outputs can be selected separately.

The files are:

- Individual aquifers: `aquifer_day.txt`, `aquifer_mon.txt`, `aquifer_yr.txt`, and `aquifer_aa.txt`.
- Basin averages: `basin_aqu_day.txt`, `basin_aqu_mon.txt`, `basin_aqu_yr.txt`, and `basin_aqu_aa.txt`.

Corresponding `.csv` files are produced when CSV output is enabled. The suffixes mean daily, monthly, yearly, and average annual.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](aquifer/jday.md) | Day of year | n/a |
| [mon](aquifer/mon.md) | Month | n/a |
| [day](aquifer/day.md) | Day of month | n/a |
| [yr](aquifer/yr.md) | Calendar year | n/a |
| [unit](aquifer/unit.md) | Aquifer identifier; basin identifier for basin output | n/a |
| [gis_id](aquifer/gis_id.md) | GIS identifier | n/a |
| [name](aquifer/name.md) | Aquifer name or basin name | n/a |
| [flo](aquifer/flo.md) | Groundwater flow leaving the aquifer | mm |
| [dep_wt](aquifer/dep_wt.md) | Depth from the ground surface to the water table | m |
| [stor](aquifer/stor.md) | Water stored in the aquifer | mm |
| [rchrg](aquifer/rchrg.md) | Recharge entering the aquifer | mm |
| [seep](aquifer/seep.md) | Seepage leaving the bottom of the aquifer | mm |
| [revap](aquifer/revap.md) | Groundwater used for evaporation and plant uptake | mm |
| [no3_st](aquifer/no3_st.md) | Nitrate nitrogen stored in the aquifer | kg N/ha |
| [minp](aquifer/minp.md) | Mineral phosphorus stored in the aquifer | kg P/ha |
| [orgn](aquifer/orgn.md) | Carbon value under a mismatched nutrient header; see note | — |
| [orgp](aquifer/orgp.md) | Organic nitrogen value under a mismatched header; see note | — |
| [no3_rchg](aquifer/no3_rchg.md) | Nitrate nitrogen entering with recharge | kg N/ha |
| [no3_loss](aquifer/no3_loss.md) | Nitrate nitrogen loss | kg N/ha |
| [no3_lat](aquifer/no3_lat.md) | Nitrate nitrogen leaving with groundwater discharge | kg N/ha |
| [no3_seep](aquifer/no3_seep.md) | Nitrate nitrogen leaving with seepage | kg N/ha |
| [flo_cha](aquifer/flo_cha.md) | Groundwater flow routed to channels | mm |
| [flo_res](aquifer/flo_res.md) | Groundwater flow routed to reservoirs | mm |
| [flo_ls](aquifer/flo_ls.md) | Groundwater flow routed to landscape objects | mm |

{% hint style="warning" %}
In the inspected main version, the columns headed `orgn` and `orgp` do not match the values written in those positions. They contain the aquifer carbon and organic-nitrogen values, respectively. Their printed nutrient labels and units should not be used to interpret these two columns until the mismatch is resolved.
{% endhint %}

For individual aquifer output, daily rows contain daily values. Monthly and yearly water exchanges accumulate over the reporting period; storage, water-table depth, and nitrate storage are averaged. Average-annual output summarizes the printed simulation years.
