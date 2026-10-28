---
description: "Defines named organic/mineral component records for outside sources used by water allocation."
---

# om_osrc.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named organic/mineral component records for outside sources used by water allocation.

SWAT+ uses the literal filename `om_osrc.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [om_osrc_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/om_osrc_read.f90#L31). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 34

Source condition/loop: `if (.not. i_exist .or. 'om_osrc.wal' == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of component-value records to allocate and read | integer | n/a | — | — |

### Data record

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
