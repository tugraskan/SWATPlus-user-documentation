---
description: "Recharge ponds: source, size, bed conductivity, weather and start date."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file defines managed recharge ponds. Its presence turns ponds on; there is no setting in `codes.gw`. The cells under each pond come from [pond_cell.gw](../pond_cell.gw/README.md), and the daily diversions from [pond_div.gw](../pond_div.gw/README.md).

SWAT+ looks for `ponds.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1913-L1977) reader.

# ponds.gw

The first two lines are a title and column headings. Then give one line per pond ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1946-L1957)).

Each day, an operating pond receives its diversion, then rain, loses evaporation, and seeps to each active cell under it ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L77-L256)). A pond with no source (`chan` and `canal` 0 and `unl` not 1) does nothing that day, not even rain or seepage.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id.md) | Pond number | integer | n/a | — | — |
| [area](area.md) | Pond surface area | real | m² | — | — |
| [chan](chan.md) | Channel that supplies the pond (0 = none) | integer | n/a | 0 | — |
| [canal](canal.md) | Diversion canal that supplies the pond (0 = none) | integer | n/a | 0 | — |
| [unl](unl.md) | 1 = supplied from outside the model | integer | n/a | 0 | 0 or 1 |
| [bed_k](bed_k.md) | Pond-bed seepage rate | real | m/day | — | — |
| [wsta](wsta.md) | Weather station for rain and PET | integer | n/a | — | — |
| [evap_co](evap_co.md) | Evaporation coefficient | real | n/a | — | 0 to 1 |
| [yr_start](yr_start.md) | First year of operation | integer | year | — | — |
| [mo_start](mo_start.md) | First month of operation | integer | month | — | 1 to 12 |
| [dy_start](dy_start.md) | First day of month of operation | integer | day | — | 1 to 31 |
| [unl_conc(j)](unl_conc_j.md) | Concentration of outside water, one per solute | real | g/m³ | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
