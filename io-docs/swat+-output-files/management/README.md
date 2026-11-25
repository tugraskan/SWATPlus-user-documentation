# Management

See [Management operation records](operation-records.md) for the row widths and values written by each operation, including the short paddy and weir records.

`mgt_out.txt` records management operations as they are executed. The table below reproduces its nominal 21-column header. Actual rows have operation-dependent widths; the common state fields apply to rows that write the full prefix, and the `op_var` and `var1` through `var7` values depend on the operation.

## How to produce this file

Set `mgtout` to `y` in the `crop_yld mgtout hydcon fdcout` settings line of [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). It is the second value on that line. SWAT+ creates `mgt_out.txt` and adds records as reportable management operations execute. This is a TXT event log. [Settings reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L39), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_mgt.f90#L7), [Example operation writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L347)

{% hint style="warning" %}
At source revision `6f515368`, some rows cannot be interpreted positionally using this header. A short `PADDY IRRIGATION` row writes six identifiers/labels followed immediately by the applied irrigation amount, which would appear under `phubase`. A separate `IRRIGATE` branch writes the whole four-component residue record at `surf_rsd`, shifting subsequent values: residue carbon and nitrogen appear under `soil_no3` and `soil_solp`, while the actual nitrate and soluble-P values appear under `var1` and `var2`. See the [two write lists](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L347) and [residue-record components](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/organic_mineral_mass_module.f90#L7). These are static source findings; execution of these branches has not been tested.
{% endhint %}

| Field | Description | Unit |
| --- | --- | --- |
| [hru](hru.md) | HRU identifier | n/a |
| [year](year.md) | Calendar year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [crop/fert/pest](crop-per-fert-per-pest.md) | Crop, fertilizer, or pesticide name associated with the operation | n/a |
| [operation](operation.md) | Management operation name | n/a |
| [phubase](phubase.md) | Base heat-unit fraction | fraction |
| [phuplant](phuplant.md) | Plant heat-unit fraction | fraction |
| [soil_water](soil_water.md) | Soil-water state at the operation | mm |
| [plant_bioms](plant_bioms.md) | Plant biomass | kg/ha |
| [surf_rsd](surf_rsd.md) | Surface residue | kg/ha |
| [soil_no3](soil_no3.md) | Soil nitrate | kg/ha |
| [soil_solp](soil_solp.md) | Soil soluble phosphorus | kg/ha |
| [op_var](op_var.md) | First operation-specific value in full-prefix rows | operation-dependent |
| [var1](var1.md) | Operation-specific value 1 | operation-dependent |
| [var2](var2.md) | Operation-specific value 2 | operation-dependent |
| [var3](var3.md) | Operation-specific value 3 | operation-dependent |
| [var4](var4.md) | Operation-specific value 4 | operation-dependent |
| [var5](var5.md) | Operation-specific value 5 | operation-dependent |
| [var6](var6.md) | Operation-specific value 6 | operation-dependent |
| [var7](var7.md) | Operation-specific value 7 | operation-dependent |

For example, normal [irrigation rows](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L156) write the applied amount at `op_var`, while [fertilizer rows](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L379) write the fertilizer amount there followed by nutrient amounts. The slot holds a value, not an intervening variable-name label.

The source units row prints `deg_c` for `phubase` and `phuplant`, but the [base heat-unit update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L230) and [plant heat-unit update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nut_demand.f90#L65) accumulate normalized heat-unit fractions. The table uses those calculation-based units.

See [Land-use change records](land-use-change-records.md) for the separate `lu_change_out.txt` report, its action-specific fields, and its unheaded values.
