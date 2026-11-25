---
description: "Initial groundwater solute concentrations by cell."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file gives each cell's initial groundwater solute concentrations. It is read only when solute transport is on and `solute.gw` exists; without it, all initial concentrations are 0.

SWAT+ looks for `cell_sol.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1665-L1675) reader.

# cell_sol.gw

The first two lines are a title and column headings. Then give `ncell` lines in cell order, each with a cell number and one concentration per solute. Solutes are always in this order: nitrate (`no3`), phosphorus (`p`), then the salt ions and the other constituents named in `constituents.cs`, in that file's order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1609-L1639)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [cell_id](cell_id.md) | Cell number; not checked | integer | n/a | — | — |
| [conc](conc.md) | Initial concentration, one per solute | real | g/m³ | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
