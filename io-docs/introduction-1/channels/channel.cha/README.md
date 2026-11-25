---
description: "This file links each channel to its initial-condition, hydrology, sediment, and nutrient parameter sets.

{% hint style="info" %}
[`proc_cha.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cha.f90#L19-L41) reads and initializes `channel.cha` records when present, but the daily `case ("chan")` dispatch in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305-L310) is commented out (`ch_rtday` has no callers). Active channel routing in SWAT+ main (`6f515368`) uses `chandeg` via [`channel-lte.cha`](../channel-lte.cha/).
{% endhint %}"
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links each channel to its initial-condition, hydrology, sediment, and nutrient parameter sets.

{% hint style="info" %}
[`proc_cha.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cha.f90#L19-L41) reads and initializes `channel.cha` records when present, but the daily `case ("chan")` dispatch in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305-L310) is commented out (`ch_rtday` has no callers). Active channel routing in SWAT+ main (`6f515368`) uses `chandeg` via [`channel-lte.cha`](../channel-lte.cha/).
{% endhint %}

# channel.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [init](init.md) | Name of the initial channel record in initial.cha that this channel data references | string | n/a | — | — |
| [hyd](hyd.md) | Name of the hydrology record in hydrology.cha that provides hydrology inputs for this channel | string | n/a | — | — |
| [sed](sed.md) | Name of the sediment record in sediment.cha that provides sediment inputs for this channel | string | n/a | — | — |
| [nut](nut.md) | Name of the nutrient record in nutrients.cha that provides nutrient inputs for this channel | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
