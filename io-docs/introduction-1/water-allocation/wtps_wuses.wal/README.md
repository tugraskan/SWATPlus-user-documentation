---
description: "This file lists the water treatment plants and water-use objects included in the simulation."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L25), the condition `if (i_exist .or. 'wtps_wuses.wal' /= "null")` always evaluates true, so the reader attempts to open `wtps_wuses.wal` even when missing. Furthermore, [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L109) calls `wallo_wtps_wuses` before `water_treatment_read` and `water_use_read`, so `db_mx%treat` and `db_mx%uses` are still `0` during the name crosswalk in [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L64-L81).
{% endhint %}

This file lists the water treatment plants and water-use objects included in the simulation.

SWAT+ looks for `wtps_wuses.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L27) reader.

# wtps_wuses.wal

After the title, supply the water treatment plant and water-use counts. Follow the headings with the plant names and then the water-use names.

## Object counts

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [wtps](wtps.md) | Number of water treatment plant objects included in the simulation | integer | n/a | — | — |
| [wuses](wuses.md) | Number of water-use objects included in the simulation | integer | n/a | — | — |

## Water treatment plants

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [wtp_name(iwtp)](wtp_name_iwtp.md) | Name of a single water treatment plant object | string | n/a | — | — |

## Water-use objects

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [wuse_name(iwuse)](wuse_name_iwuse.md) | Name of a single water-use object | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
