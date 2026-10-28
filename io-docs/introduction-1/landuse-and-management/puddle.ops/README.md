---
description: "This file defines puddling operations used to change soil hydraulic conductivity and sediment concentration in HRU water storage."
---

{% hint style="info" %}
An exporter for this file has not been verified in SWAT+ Editor. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines puddling operations used to change soil hydraulic conductivity and sediment concentration in HRU water storage.

SWAT+ looks for `puddle.ops` in the simulation working directory; it is not selected through `file.cio`. See the [mgt_read_puddle.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_puddle.f90#L23) reader.

# puddle.ops

The first line is a title and the second line contains column headings. Add one row for each named operation, with the fields in the order below.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Puddling operation name | string | n/a | — | — |
| [wet_hc](wet_hc.md) | Hydraulic conductivity after puddling | real | mm/h | — | — |
| [sed](sed.md) | Sediment concentration after puddling | real | ppm | — | — |
| [orgn](orgn.md) | Organic nitrogen concentration; currently not used | real | ppm | — | — |
| [sedp](sedp.md) | Organic phosphorus concentration; currently not used | real | ppm | — | — |
| [no3](no3.md) | Nitrate nitrogen concentration; currently not used | real | ppm | — | — |
| [solp](solp.md) | Soluble phosphorus concentration; currently not used | real | ppm | — | — |
| [nh3](nh3.md) | Ammonia concentration; currently not used | real | ppm | — | — |
| [no2](no2.md) | Nitrite concentration; currently not used | real | ppm | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
