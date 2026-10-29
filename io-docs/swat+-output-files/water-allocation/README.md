# Water Allocation

Water-allocation output has three distinct report families. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa` where the source opens that interval. TXT and CSV variants share the same data headings when both are enabled.

## Allocation transactions

{% hint style="warning" %}
The printed 25-column header is followed by hierarchical POU, POD, and POR rows of different widths. These labels do not form one fixed rectangular data-row schema, so the attribute pages link to the relevant writer rather than assigning one universal value declaration.
{% endhint %}

The `water_allo_*` files report demands, withdrawals, and unmet demand for as many as three sources.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-allocation-transactions.md), [mon](mon-allocation-transactions.md), [day](day-allocation-transactions.md), [yr](yr-allocation-transactions.md) | Reporting date | n/a |
| [unit](unit.md) | Allocation-rule identifier | n/a |
| [trn_typ](trn_typ.md), [trn_num](trn_num.md) | Transfer object type and number | n/a |
| [drcv_typ](drcv_typ.md), [rcv_num](rcv_num.md) | Demand receiver type and number | n/a |
| [src1_obj](src1_obj.md), [src1_typ](src1_typ.md), [src1_num](src1_num.md) | First source object, type, and number | n/a |
| [demand](demand-allocation-transactions.md), [src1_withdraw](src1_withdraw.md), [src1_unmet](src1_unmet.md) | First-source demand, withdrawal, and unmet demand | m3 |
| [src2_typ](src2_typ.md), [src2_num](src2_num.md), [demand](demand-allocation-transactions-2.md), [src2_withdraw](src2_withdraw.md), [src2_unmet](src2_unmet.md) | Second source and its demand result | m3 for demand values |
| [src3_typ](src3_typ.md), [src3_num](src3_num.md), [demand](demand-allocation-transactions-3.md), [src3_withdraw](src3_withdraw.md), [src3_unmet](src3_unmet.md) | Third source and its demand result | m3 for demand values |

The printed header repeats the literal heading `demand` for all three source blocks.

## Water use and treatment

The `wallo_use_*` and `wallo_treat_*` files report a routed water-quality hydrograph for each use or treatment object.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-water-use-and-treatment.md), [mon](mon-water-use-and-treatment.md), [day](day-water-use-and-treatment.md), [yr](yr-water-use-and-treatment.md) | Reporting date | n/a |
| [name](name.md), [use](use.md) | Object name and use identifier | n/a |
| [flo](flo.md) | Water volume | m3 |
| [sed](sed.md) | Sediment | tons |
| [orgn](orgn.md), [sedp](sedp.md), [no3](no3.md), [solp](solp.md), [chla](chla.md), [nh3](nh3.md), [no2](no2.md), [cbod](cbod.md), [dox](dox.md) | Nutrient and water-quality loads | kg |
| [san](san.md), [sil](sil.md), [cla](cla.md), [sag](sag.md), [lag](lag.md), [grv](grv.md) | Particle-size loads | tons |
| [null](null.md) | Printed terminal placeholder | n/a |
