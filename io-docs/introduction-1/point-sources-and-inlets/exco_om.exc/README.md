---
description: "This file supplies named organic/mineral export-coefficient values for hydrograph components."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named organic/mineral export-coefficient (`hyd_output`) records. SWAT+ selects it from `file.cio` (`in_exco%om`, default `"exco_om.exc"`) and reads it with [`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L28-L87).

During initialization and simulation, `exco` records enter calculations along four pathways:
1. **Standalone `exco` objects:** [`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L83) copies `exco(iexco_om)` directly to `ob(iob)%hd(1)`.
2. **Routing-unit `exco` elements:** [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L100) multiplies `exco(ob(iob)%props)` component-wise by the element delivery ratio `delrto`.
3. **Recall `type = 4` records:** [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L188) copies `exco(iexco_om)` into `recall(i)%hd(1,1)` when `exco_db(iexco_om)%name == recall(i)%filename`.
4. **Water-allocation outflow quality:** [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L82), [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L54), and [`wallo_use.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L50) assign `outflo_om = exco(iom)`.

# exco\_om.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L59)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [exco\_om\_name](exco_om_name.md) | Name identifying this component-value record | string | n/a | — | — |
| [flo](flo.md) | Water-flow component value | real | `m^3` | 0 | — |
| [sed](sed.md) | Sediment component value | real | metric tons | 0 | — |
| [orgn](orgn.md) | Organic-nitrogen component value | real | kg N | 0 | — |
| [sedp](sedp.md) | Organic-phosphorus component value | real | kg P | 0 | — |
| [no3](no3.md) | Nitrate-nitrogen component value | real | kg N | 0 | — |
| [solp](solp.md) | Mineral (soluble) phosphorus component value | real | kg P | 0 | — |
| [chla](chla.md) | Chlorophyll-a component value | real | kg | 0 | — |
| [nh3](nh3.md) | Ammonia-nitrogen component value | real | kg N | 0 | — |
| [no2](no2.md) | Nitrite-nitrogen component value | real | kg N | 0 | — |
| [cbod](cbod.md) | Carbonaceous biological oxygen demand component value | real | kg | 0 | — |
| [dox](dox.md) | Dissolved-oxygen component value | real | kg | 0 | — |
| [san](san.md) | Detached sand component value | real | tons | 0 | — |
| [sil](sil.md) | Detached silt component value | real | tons | 0 | — |
| [cla](cla.md) | Detached clay component value | real | tons | 0 | — |
| [sag](sag.md) | Detached small-aggregate component value | real | tons | 0 | — |
| [lag](lag.md) | Detached large-aggregate component value | real | tons | 0 | — |
| [grv](grv.md) | Gravel component value | real | tons | 0 | — |
| [temp](temp.md) | Water-temperature component value | real | deg C | 0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
