---
description: "This file contains groundwater solute transport and reaction parameters."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains groundwater solute transport and reaction parameters.

SWAT+ looks for `solute.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1593) reader.

# solute.gw

After the title and column headings, supply the transport substep count and longitudinal dispersivity, then one row per configured solute.

## Transport substeps

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_ts_transport](num_ts_transport.md) | Number of transport time steps per day used to subdivide the groundwater time step for solute transport calculations | integer | n/a | — | — |

## Longitudinal dispersivity

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_long_disp](gw_long_disp.md) | Aquifer longitudinal dispersivity controlling the spreading of solute plumes along the direction of groundwater flow | real | — | — | — |

## Solute parameters

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [gwsol_sorb](gwsol_sorb.md) | Sorption coefficient for the solute | real | — | — | — |
| [gwsol_rctn](gwsol_rctn.md) | First-order reaction rate for the solute | real | — | — | — |
| [canal_out_conc](canal_out_conc.md) | Solute concentration in canals that receive outside water | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
