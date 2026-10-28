---
description: "Defines solute transport parameters for groundwater flow simulations, including transport time step subdivision, aquifer longitudinal dispersivity, and per-solute reaction, sorption, and canal outflow concentration values. The file is read conditionally when groundwater solute transport is enabled and the file exists, followed by a data record listing each solute by name with its associated parameters."
---

# solute.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines solute transport parameters for groundwater flow simulations, including transport time step subdivision, aquifer longitudinal dispersivity, and per-solute reaction, sorption, and canal outflow concentration values. The file is read conditionally when groundwater solute transport is enabled and the file exists, followed by a data record listing each solute by name with its associated parameters.

SWAT+ uses the literal filename `solute.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1593). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Additional read at line 1647

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_ts_transport](num_ts_transport.md) | Number of transport time steps per day used to subdivide the groundwater time step for solute transport calculations | integer | n/a | — | — |

### Additional read at line 1648

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_long_disp](gw_long_disp.md) | Aquifer longitudinal dispersivity controlling the spreading of solute plumes along the direction of groundwater flow | real | — | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier name for the solute being defined in the data record | string | n/a | — | — |
| [gwsol_sorb](gwsol_sorb.md) | Sorption coefficient for the solute, used to scale mass accumulation in advection, dispersion, and reaction terms by the transport time step | real | — | — | — |
| [gwsol_rctn](gwsol_rctn.md) | First-order reaction rate for the solute, multiplied by cell concentration and groundwater volume to compute reaction mass changes | real | — | — | — |
| [canal_out_conc](canal_out_conc.md) | Solute concentration in canals that receive outside water, used to compute solute mass loads from canal discharge | real | — | — | — |
