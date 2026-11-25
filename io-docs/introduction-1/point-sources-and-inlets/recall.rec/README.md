---
description: Master list of recall inputs
---

# recall.rec

This file lists the organic/mineral recall inputs used in a simulation. SWAT+ selects this file from `file.cio` (`in_rec%recall_rec`, default `"recall.rec"`) and reads it with [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L50-L198). The first two lines contain a title and column headings; each following data row is read list-directed as `k`, `name`, `typ`, and `filename` ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L80)).

Recall records are linked to spatial objects through `recall.con` (see [`'object'.con`](../../connectivity/hru.con/README.md)) and routed during simulation by [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L320-L356). Recall hydrographs are also referenced by reservoir decision-table releases ([`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L232-L238)) and water-allocation routines ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L74-L82), [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L46-L54), and [`wallo_use.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L42-L50)).

{% hint style="warning" %}
For `type = 4`, [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L182-L191) matches `fname` against `exco_db(iexco_om)%name` and copies `exco(iexco_om)` into `recall(i)%hd(1,1)` (indexing `exco` directly by the loop counter `iexco_om`). However, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L320-L347) only handles `type` values `0`–`3` (there is no `case (4)` branch for `recall` objects), whereas water-allocation routines fall through to `exco(iom)`.
{% endhint %}

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num](num.md) | Recall input record number | integer | n/a | — | — |
| [name](name.md) | User label for the recall input; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [type](type.md) | Recall type: `0`=subdaily, `1`=daily, `2`=monthly, `3`=yearly, `4`=EXCO/average-annual constant | integer | n/a | 0 | 0–4 |
| [fname](fname.md) | Time-series filename for types `0`–`3`; EXCO database record name for type `4` | string | n/a | — | — |
