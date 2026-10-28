---
description: "This file supplies named organic/mineral delivery values for water, sediment, and other hydrograph components."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named organic/mineral delivery values for water, sediment, and other hydrograph components.

# dr_om.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_om_name](dr_om_name.md) | Name identifying this organic/mineral delivery record | string | n/a | — | — |
| [flo](flo.md) | Water-flow component value for this named record | real | — | — | — |
| [sed](sed.md) | Sediment component value for this named record | real | — | — | — |
| [orgn](orgn.md) | Organic-nitrogen component value for this named record | real | — | — | — |
| [sedp](sedp.md) | Organic-phosphorus component value for this named record | real | — | — | — |
| [no3](no3.md) | Nitrate-nitrogen component value for this named record | real | — | — | — |
| [solp](solp.md) | Soluble-phosphorus component value for this named record | real | — | — | — |
| [chla](chla.md) | Chlorophyll-a component value for this named record | real | — | — | — |
| [nh3](nh3.md) | Ammonia-nitrogen component value for this named record | real | — | — | — |
| [no2](no2.md) | Nitrite-nitrogen component value for this named record | real | — | — | — |
| [cbod](cbod.md) | Carbonaceous biological oxygen demand component value for this named record | real | — | — | — |
| [dox](dox.md) | Dissolved-oxygen component value for this named record | real | — | — | — |
| [san](san.md) | Sand component value for this named record | real | — | — | — |
| [sil](sil.md) | Silt component value for this named record | real | — | — | — |
| [cla](cla.md) | Clay component value for this named record | real | — | — | — |
| [sag](sag.md) | Small-aggregate component value for this named record | real | — | — | — |
| [lag](lag.md) | Large-aggregate component value for this named record | real | — | — | — |
| [grv](grv.md) | Gravel component value for this named record | real | — | — | — |
| [temp](temp.md) | Water-temperature component value for this named record | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
