---
description: "This file lists the water treatment plants and water-use objects included in the simulation."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the water treatment plants and water-use objects included in the simulation.

SWAT+ looks for `wtps_wuses.wal` in the simulation working directory; it is not selected through `file.cio`. See the [wallo_wtps_wuses.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_wtps_wuses.f90#L27) reader.

# wtps_wuses.wal

After the title, supply the water treatment plant and water-use counts. Follow the headings with the plant names and then the water-use names.

## Object counts

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wtps](wtps.md) | Number of water treatment plant objects included in the simulation | integer | n/a | — | — |
| [wuses](wuses.md) | Number of water use objects included in the simulation | integer | n/a | — | — |

## Water treatment plants

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wtp_name(iwtp)](wtp_name_iwtp.md) | Name of a single water treatment plant object | string | n/a | — | — |

## Water-use objects

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wuse_name(iwuse)](wuse_name_iwuse.md) | Name of a single water use object | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
