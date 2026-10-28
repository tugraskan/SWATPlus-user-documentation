---
description: "This file supplies named organic/mineral component values for outside water sources."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named organic/mineral component values for outside water sources.

SWAT+ looks for `om_osrc.wal` in the simulation working directory; it is not selected through `file.cio`. See the [om_osrc_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/om_osrc_read.f90#L31) reader.

# om_osrc.wal

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

## Number of records

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [om_osrc_name](om_osrc_name.md) | Name identifying this component-value record | string | n/a | — | — |
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
