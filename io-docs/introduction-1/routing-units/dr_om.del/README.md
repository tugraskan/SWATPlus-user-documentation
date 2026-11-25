---
description: "This file supplies named organic/mineral delivery values for water, sediment, and other hydrograph components."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named organic/mineral delivery ratios for water, sediment, and other hydrograph components, read by [`dr_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L60). Each numeric column is a dimensionless multiplier stored in a `hyd_output` structure (Fortran struct default: `0.`) and applied component-wise by [`hydout_mult`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1391-L1413); `temp` is parsed into memory but ignored during multiplication.

# dr\_om.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dr\_om\_name](dr_om_name.md) | Name identifying this organic/mineral delivery record | string | n/a | — | — |
| [flo](flo.md) | Water-flow delivery ratio for this named record | real | fraction | — | — |
| [sed](sed.md) | Sediment delivery ratio for this named record | real | fraction | — | — |
| [orgn](orgn.md) | Organic-nitrogen delivery ratio for this named record | real | fraction | — | — |
| [sedp](sedp.md) | Organic-phosphorus delivery ratio for this named record | real | fraction | — | — |
| [no3](no3.md) | Nitrate-nitrogen delivery ratio for this named record | real | fraction | — | — |
| [solp](solp.md) | Soluble-phosphorus delivery ratio for this named record | real | fraction | — | — |
| [chla](chla.md) | Chlorophyll-a delivery ratio for this named record | real | fraction | — | — |
| [nh3](nh3.md) | Ammonia-nitrogen delivery ratio for this named record | real | fraction | — | — |
| [no2](no2.md) | Nitrite-nitrogen delivery ratio for this named record | real | fraction | — | — |
| [cbod](cbod.md) | Carbonaceous biological oxygen demand delivery ratio for this named record | real | fraction | — | — |
| [dox](dox.md) | Dissolved-oxygen delivery ratio for this named record | real | fraction | — | — |
| [san](san.md) | Sand delivery ratio for this named record | real | fraction | — | — |
| [sil](sil.md) | Silt delivery ratio for this named record | real | fraction | — | — |
| [cla](cla.md) | Clay delivery ratio for this named record | real | fraction | — | — |
| [sag](sag.md) | Small-aggregate delivery ratio for this named record | real | fraction | — | — |
| [lag](lag.md) | Large-aggregate delivery ratio for this named record | real | fraction | — | — |
| [grv](grv.md) | Gravel delivery ratio for this named record | real | fraction | — | — |
| [temp](temp.md) | Water-temperature value (read but not used by the model) | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
