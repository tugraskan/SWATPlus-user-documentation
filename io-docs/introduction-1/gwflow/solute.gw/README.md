---
description: "Groundwater solute transport settings and per-solute parameters."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file holds the transport settings and the parameters of each groundwater solute. It is read only when `solute` is 1 in [codes.gw](../codes.gw/solute.md).

SWAT+ looks for `solute.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1593-L1664) reader.

# solute.gw

Each item is on its own line, in this order: a title line, a heading line, `num_ts_transport`, `gw_long_disp`, one more line that is skipped, then one line per solute: `name gwsol_sorb gwsol_rctn canal_out_conc` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1645-L1658)). Solutes are always in this order: nitrate (`no3`), phosphorus (`p`), then the salt ions and the other constituents named in `constituents.cs`, in that file's order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1609-L1639)). Values after the fourth on a solute line are not read; SWAT+ Editor writes an initial concentration there, but initial concentrations come from [cell_sol.gw](../cell_sol.gw/README.md).

When `constituents.cs` lists other constituents (selenium and boron), the reader then tries to read reaction-group and shale data, but from the file unit it has already closed ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1664-L1731)). This is listed in `MODEL_ISSUES.md`.

## Transport settings

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num_ts_transport](num_ts_transport.md) | Transport sub-steps per flow step | integer | n/a | — | 1 or more |
| [gw_long_disp](gw_long_disp.md) | Longitudinal dispersivity | real | m | — | — |

## Solute parameters

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Solute name; not checked | string | n/a | — | — |
| [gwsol_sorb](gwsol_sorb.md) | Retardation factor (1 = no sorption) | real | n/a | — | 1 or more |
| [gwsol_rctn](gwsol_rctn.md) | First-order reaction rate (negative = decay) | real | 1/day | — | — |
| [canal_out_conc](canal_out_conc.md) | Concentration in canal seepage water | real | g/m³ | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
