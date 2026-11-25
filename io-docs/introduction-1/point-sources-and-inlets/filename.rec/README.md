---
description: Organic and mineral time-series data for a point source or inlet
---

# 'om\_filename'.rec

This file supplies organic and mineral time-series data for a point source or inlet referenced by [`recall.rec`](../recall.rec/README.md) when `type` is `0` (subdaily), `1` (daily), `2` (monthly), or `3` (yearly). It is opened on unit `108` by [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L89-L178).

Line 1 contains a file title ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L90)), line 2 contains `nbyr` ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L92)), and line 3 contains column headings ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L94)). Each following data row is read list-directed into the date/identifier fields and the 18 `hyd_output` components ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L164-L171)).

## Header line (line 2)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nbyr](nbyr.md) | Number of years listed on line 2; parsed into a local variable while arrays allocate using `time%nbyr` | integer | yr | — | — |

## Data rows (line 4 onward)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [jday](jday.md) | Julian day (subdaily step index for `type = 0`; day of year for `type = 1`) | integer | n/a | — | 1–366 |
| [mo](mo.md) | Calendar month | integer | n/a | — | 1–12 |
| [day\_mo](day_mo.md) | Day of month; read but not used in SWAT+ main (`6f515368`) | integer | n/a | — | 1–31 |
| [yr](yr.md) | Calendar year | integer | yr | — | — |
| [ob\_typ](ob_typ.md) | Object type label; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [ob\_name](ob_name.md) | Object name label; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [flo](flo.md) | Water flow (`m^3` per step for `type` `1`–`3`; `m^3/s` for subdaily `type = 0`; negative values divert from channel) | real | `m^3` or `m^3/s` | 0 | — |
| [sed](sed.md) | Sediment load | real | metric tons | 0 | — |
| [orgn](orgn.md) | Organic nitrogen load | real | kg N | 0 | — |
| [sedp](sedp.md) | Organic phosphorus load | real | kg P | 0 | — |
| [no3](no3.md) | Nitrate-nitrogen load | real | kg N | 0 | — |
| [solp](solp.md) | Mineral (soluble) phosphorus load | real | kg P | 0 | — |
| [chla](chla.md) | Chlorophyll-a load | real | kg | 0 | — |
| [nh3](nh3.md) | Ammonia-nitrogen load | real | kg N | 0 | — |
| [no2](no2.md) | Nitrite-nitrogen load | real | kg N | 0 | — |
| [cbod](cbod.md) | Carbonaceous biological oxygen demand load | real | kg | 0 | — |
| [dox](dox.md) | Dissolved oxygen load | real | kg | 0 | — |
| [san](san.md) | Detached sand load | real | tons | 0 | — |
| [sil](sil.md) | Detached silt load | real | tons | 0 | — |
| [cla](cla.md) | Detached clay load | real | tons | 0 | — |
| [sag](sag.md) | Detached small-aggregate load | real | tons | 0 | — |
| [lag](lag.md) | Detached large-aggregate load | real | tons | 0 | — |
| [grv](grv.md) | Gravel load | real | tons | 0 | — |
| [temp](temp.md) | Water temperature | real | deg C | 0 | — |
