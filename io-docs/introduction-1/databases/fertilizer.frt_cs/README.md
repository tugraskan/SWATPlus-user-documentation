---
description: This file contains constituent composition values for fertilizers.
---

# fertilizer.frt_cs

{% hint style="info" %}
This file is supported by the SWAT+ model, but no exporter was found in the inspected SWAT+ Editor version. It may need to be supplied separately. Editor checkout checked: `1efec55`.

The table below is based on the SWAT+ Fortran source code. Its contents should not be assumed to match the labels, defaults, or options available in SWAT+ Editor. A dash means that no recommended default or range has been established here; it is not a Fortran initialization value.
{% endhint %}

Constituent composition of fertilizer for the SeO4 and SeO3 species and boron. Application routines multiply these mass fractions by the amount of fertilizer applied.

SWAT+ looks directly for the literal filename `fertilizer.frt_cs` in the simulation working directory; this filename is not selected through `file.cio`. It is read by [cs_fert_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cs_fert_read.f90#L25). If the file is absent, no constituent-fertilizer composition records are loaded from it.

The first line is a title and the second line is a header. Each subsequent record contains the fields below, in this order. There is no separate record-count line. The reader requests exactly one record per fertilizer database entry (db_mx%fertparm). Keep these records in the same order as the fertilizer database; the name field is not used to reorder them.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [fertnm](fertnm.md) | Fertilizer name label | string | n/a | — | — |
| [seo4](seo4.md) | SeO4 constituent mass fraction | real | kg/kg fertilizer | — | — |
| [seo3](seo3.md) | SeO3 constituent mass fraction | real | kg/kg fertilizer | — | — |
| [boron](boron.md) | boron constituent mass fraction | real | kg/kg fertilizer | — | — |

Recommended defaults and ranges are not specified by this page. The dash does not imply a default of zero.

The values are mass per mass of fertilizer: multiplying kg fertilizer/ha by kg constituent/kg fertilizer gives kg constituent/ha. They are not absolute application loads in kg/ha, despite the older source comments. No required sum of the constituent values is established here.
