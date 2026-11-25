---
description: "This file links a channel initial-condition set to its constituent initialization records."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links a channel initial-condition set to its constituent initialization records.

SWAT+ looks for `initial.cha_cs` in the simulation working directory; it is not selected through `file.cio`. [`ch_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_init_cs.f90#L27-L51) loads `ch_init_cs`, and [`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L227-L270) matches channels by `name` in [**initial.cha**](../../channels/initial.cha/) and reuses that row index `isp_ini` into `ch_init_cs(isp_ini)` for `path`, `salt`, and `cs`—rows must align with `initial.cha`. In SWAT+ main (`6f515368`), `name`, `pest`, and `hmet` in `initial.cha_cs` are unused.

# initial.cha\_cs

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name (read but not matched; row alignment with `initial.cha` is used) | string | n/a | — | — |
| [pest](pest.md) | Intended pesticide initialization pointer (read but not used; `initial.cha` `pest` is used) | string | n/a | — | — |
| [path](path.md) | Name of the referenced pathogen initialization record | string | n/a | — | — |
| [hmet](hmet.md) | Intended heavy-metal initialization pointer (read but not used) | string | n/a | — | — |
| [salt](salt.md) | Name of the referenced salt initialization record | string | n/a | — | — |
| [cs](cs.md) | Name of the referenced general-constituent initialization record | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
