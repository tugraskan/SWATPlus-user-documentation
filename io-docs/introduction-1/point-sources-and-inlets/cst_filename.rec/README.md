---
description: General-constituent time-series recall file format
---

# 'cst\_filename'.rec

This file supplies general-constituent time-series data for a point source or inlet referenced by [`cs_recall.rec`](../cs_recall.rec/README.md).

{% hint style="warning" %}
Although [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L113-L230) implements this reader (opened on unit `108` for `typ` `1`–`3`) and [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L356) invokes [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L3-L103) when `cs_db%num_cs > 0`, **`recall_read_cs` is not called anywhere in SWAT+ main (`6f515368`)**.
{% endhint %}

Line 1 contains a file title ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L114)), line 2 contains `nbyr` ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L116)), and line 3 contains column headings ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L118)), which also determines whether the source is inside (`pts_type = 1`) or outside (`pts_type = 2`) the watershed ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L123-L125)). Each following row reads the date/identifier columns and `cs_db%num_cs` constituent values ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L199)).

## Header line (line 2)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](nbyr.md) | Number of years of constituent recall data used to allocate `hd_cs` | integer | yr | — | — |

## Data rows (line 4 onward)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [jday](jday.md) | Julian day (day of year for `typ = 1`) | integer | n/a | — | 1–366 |
| [mo](mo.md) | Calendar month (month index for `typ = 2`) | integer | n/a | — | 1–12 |
| [day\_mo](day_mo.md) | Day of month; read but not used in calculations | integer | n/a | — | 1–31 |
| [yr](yr.md) | Calendar year | integer | yr | — | — |
| [ob\_typ](ob_typ.md) | Object type label; read but not used in calculations | string | n/a | — | — |
| [ob\_name](ob_name.md) | Object name label; read but not used in calculations | string | n/a | — | — |
| [cs(ics)](cs_ics.md) | General-constituent load for each constituent (`1` to `cs_db%num_cs`) | real | kg | 0 | — |
