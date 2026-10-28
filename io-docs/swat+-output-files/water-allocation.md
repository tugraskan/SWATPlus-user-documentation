# Water Allocation

Water-allocation output has three distinct report families. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa` where the source opens that interval. TXT and CSV variants share the same data headings when both are enabled.

## Allocation transactions

The `water_allo_*` files report demands, withdrawals, and unmet demand for as many as three sources.

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr | Reporting date | n/a |
| unit | Allocation-rule identifier | n/a |
| trn_typ, trn_num | Transfer object type and number | n/a |
| drcv_typ, rcv_num | Demand receiver type and number | n/a |
| src1_obj, src1_typ, src1_num | First source object, type, and number | n/a |
| demand, src1_withdraw, src1_unmet | First-source demand, withdrawal, and unmet demand | m3 |
| src2_typ, src2_num, demand, src2_withdraw, src2_unmet | Second source and its demand result | m3 for demand values |
| src3_typ, src3_num, demand, src3_withdraw, src3_unmet | Third source and its demand result | m3 for demand values |

The printed header repeats the literal heading `demand` for all three source blocks.

## Water use and treatment

The `wallo_use_*` and `wallo_treat_*` files report a routed water-quality hydrograph for each use or treatment object.

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr | Reporting date | n/a |
| name, use | Object name and use identifier | n/a |
| flo | Water volume | m3 |
| sed | Sediment | tons |
| orgn, sedp, no3, solp, chla, nh3, no2, cbod, dox | Nutrient and water-quality loads | kg |
| san, sil, cla, sag, lag, grv | Particle-size loads | tons |
| null | Printed terminal placeholder | n/a |
