---
description: "Defines named organic/mineral export-coefficient records with a value for each hydrograph component. Routing behavior depends on the objects that reference the record."
---

# exco_om.exc

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named organic/mineral export-coefficient records with a value for each hydrograph component. Routing behavior depends on the objects that reference the record.

The reader obtains the filename through `in_exco%om`.

{% hint style="warning" %}
Source limitation: Initialization named-row crosswalk and RU direct-row routing differ; no universal coefficient/unit interpretation. These pages describe the inspected source and do not establish a working runtime configuration.
{% endhint %}

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_om_name](exco_om_name.md) | Name identifying this component-value record | string | n/a | — | — |
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
