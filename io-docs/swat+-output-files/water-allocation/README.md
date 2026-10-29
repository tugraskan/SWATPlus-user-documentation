# Water Allocation

Water-allocation output has three distinct report families. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa` where the source opens that interval. TXT and CSV variants share the same data headings when both are enabled.

## Allocation transactions

{% hint style="warning" %}
The printed 25-column header is followed by hierarchical POU, POD, and POR rows of different widths. These labels do not form one fixed rectangular data-row schema, so the attribute pages link to the relevant writer rather than assigning one universal value declaration.
{% endhint %}

The `water_allo_*` files report demands, withdrawals, and unmet demand for as many as three sources.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-allocation-transactions.md) | Day of year | n/a |
| [mon](mon-allocation-transactions.md) | Month | n/a |
| [day](day-allocation-transactions.md) | Day of month | n/a |
| [yr](yr-allocation-transactions.md) | Calendar year | n/a |
| [unit](unit.md) | Allocation-rule identifier | n/a |
| [trn_typ](trn_typ.md) | Transfer object type | n/a |
| [trn_num](trn_num.md) | Transfer object number | n/a |
| [drcv_typ](drcv_typ.md) | Demand receiver type | n/a |
| [rcv_num](rcv_num.md) | Demand receiver number | n/a |
| [src1_obj](src1_obj.md) | First source object | n/a |
| [src1_typ](src1_typ.md) | First source type | n/a |
| [src1_num](src1_num.md) | First source number | n/a |
| [demand](demand-allocation-transactions.md) | First-source demand | m3 |
| [src1_withdraw](src1_withdraw.md) | First source withdrawal | m3 |
| [src1_unmet](src1_unmet.md) | First source unmet demand | m3 |
| [src2_typ](src2_typ.md) | Second source type | n/a |
| [src2_num](src2_num.md) | Second source number | n/a |
| [demand](demand-allocation-transactions-2.md) | Second-source demand | m3 |
| [src2_withdraw](src2_withdraw.md) | Second source withdrawal | m3 |
| [src2_unmet](src2_unmet.md) | Second source unmet demand | m3 |
| [src3_typ](src3_typ.md) | Third source type | n/a |
| [src3_num](src3_num.md) | Third source number | n/a |
| [demand](demand-allocation-transactions-3.md) | Third-source demand | m3 |
| [src3_withdraw](src3_withdraw.md) | Third source withdrawal | m3 |
| [src3_unmet](src3_unmet.md) | Third source unmet demand | m3 |

The printed header repeats the literal heading `demand` for all three source blocks.

## Water use and treatment

The `wallo_use_*` and `wallo_treat_*` files report a routed water-quality hydrograph for each use or treatment object.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-water-use-and-treatment.md) | Day of year | n/a |
| [mon](mon-water-use-and-treatment.md) | Month | n/a |
| [day](day-water-use-and-treatment.md) | Day of month | n/a |
| [yr](yr-water-use-and-treatment.md) | Calendar year | n/a |
| [name](name.md) | Object name | n/a |
| [use](use.md) | Water-use identifier | n/a |
| [flo](flo.md) | Water volume | m3 |
| [sed](sed.md) | Sediment | tons |
| [orgn](orgn.md) | Organic nitrogen load | kg |
| [sedp](sedp.md) | Sediment-associated phosphorus load | kg |
| [no3](no3.md) | Nitrate nitrogen load | kg |
| [solp](solp.md) | Soluble phosphorus load | kg |
| [chla](chla.md) | Chlorophyll a load | kg |
| [nh3](nh3.md) | Ammonia load | kg |
| [no2](no2.md) | Nitrite load | kg |
| [cbod](cbod.md) | Carbonaceous biochemical oxygen demand load | kg |
| [dox](dox.md) | Dissolved oxygen load | kg |
| [san](san.md) | Sand load | tons |
| [sil](sil.md) | Silt load | tons |
| [cla](cla.md) | Clay load | tons |
| [sag](sag.md) | Small aggregates load | tons |
| [lag](lag.md) | Large aggregates load | tons |
| [grv](grv.md) | Gravel load | tons |
| [null](null.md) | Printed terminal placeholder | n/a |
