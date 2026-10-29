# Water Allocation

Water-allocation output has three distinct report families. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa` where the source opens that interval. TXT and CSV variants share the same data headings when both are enabled.

## Allocation transactions

{% hint style="warning" %}
The printed 25-column header is followed by hierarchical POU, POD, and POR rows of different widths. These labels do not form one fixed rectangular data-row schema, so the attribute pages link to the relevant writer rather than assigning one universal value declaration.
{% endhint %}

The `water_allo_*` files report demands, withdrawals, and unmet demand for as many as three sources.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](water-allocation/jday-allocation-transactions.md), [mon](water-allocation/mon-allocation-transactions.md), [day](water-allocation/day-allocation-transactions.md), [yr](water-allocation/yr-allocation-transactions.md) | Reporting date | n/a |
| [unit](water-allocation/unit.md) | Allocation-rule identifier | n/a |
| [trn_typ](water-allocation/trn_typ.md), [trn_num](water-allocation/trn_num.md) | Transfer object type and number | n/a |
| [drcv_typ](water-allocation/drcv_typ.md), [rcv_num](water-allocation/rcv_num.md) | Demand receiver type and number | n/a |
| [src1_obj](water-allocation/src1_obj.md), [src1_typ](water-allocation/src1_typ.md), [src1_num](water-allocation/src1_num.md) | First source object, type, and number | n/a |
| [demand](water-allocation/demand-allocation-transactions.md), [src1_withdraw](water-allocation/src1_withdraw.md), [src1_unmet](water-allocation/src1_unmet.md) | First-source demand, withdrawal, and unmet demand | m3 |
| [src2_typ](water-allocation/src2_typ.md), [src2_num](water-allocation/src2_num.md), [demand](water-allocation/demand-allocation-transactions-2.md), [src2_withdraw](water-allocation/src2_withdraw.md), [src2_unmet](water-allocation/src2_unmet.md) | Second source and its demand result | m3 for demand values |
| [src3_typ](water-allocation/src3_typ.md), [src3_num](water-allocation/src3_num.md), [demand](water-allocation/demand-allocation-transactions-3.md), [src3_withdraw](water-allocation/src3_withdraw.md), [src3_unmet](water-allocation/src3_unmet.md) | Third source and its demand result | m3 for demand values |

The printed header repeats the literal heading `demand` for all three source blocks.

## Water use and treatment

The `wallo_use_*` and `wallo_treat_*` files report a routed water-quality hydrograph for each use or treatment object.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](water-allocation/jday-water-use-and-treatment.md), [mon](water-allocation/mon-water-use-and-treatment.md), [day](water-allocation/day-water-use-and-treatment.md), [yr](water-allocation/yr-water-use-and-treatment.md) | Reporting date | n/a |
| [name](water-allocation/name.md), [use](water-allocation/use.md) | Object name and use identifier | n/a |
| [flo](water-allocation/flo.md) | Water volume | m3 |
| [sed](water-allocation/sed.md) | Sediment | tons |
| [orgn](water-allocation/orgn.md), [sedp](water-allocation/sedp.md), [no3](water-allocation/no3.md), [solp](water-allocation/solp.md), [chla](water-allocation/chla.md), [nh3](water-allocation/nh3.md), [no2](water-allocation/no2.md), [cbod](water-allocation/cbod.md), [dox](water-allocation/dox.md) | Nutrient and water-quality loads | kg |
| [san](water-allocation/san.md), [sil](water-allocation/sil.md), [cla](water-allocation/cla.md), [sag](water-allocation/sag.md), [lag](water-allocation/lag.md), [grv](water-allocation/grv.md) | Particle-size loads | tons |
| [null](water-allocation/null.md) | Printed terminal placeholder | n/a |
