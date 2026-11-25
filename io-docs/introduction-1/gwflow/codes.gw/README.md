---
description: "Settings that control GWFlow processes and output."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file holds the settings that control GWFlow processes and output.

SWAT+ looks for `codes.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L225-L261) reader. GWFlow runs only when `gwflow` is 1 in [codes.bsn](../../basin-1/codes.bsn/gwflow.md) and `chancell.gw` is present ([`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L46-L68)).

# codes.gw

The file has a title line, a line of setting names and a line of values. Each value belongs to the name above it; names and values are split on spaces, so a value cannot contain a space. The names may be in any order. Unrecognized names are ignored, and a setting that is not listed keeps its starting value, which is 0 (off) for every number ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L226-L260)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [grid_type](grid_type.md) | Grid layout: `structured` or `unstructured` | string | n/a | — | structured, unstructured |
| [ncell](ncell.md) | Number of groundwater cells | integer | n/a | — | — |
| [cell_size](cell_size.md) | Cell size; not used by the model | real | m | — | — |
| [n_rows](n_rows.md) | Rows of a structured grid | integer | n/a | — | — |
| [n_cols](n_cols.md) | Columns of a structured grid | integer | n/a | — | — |
| [bc_type](bc_type.md) | Default boundary type for boundary cells (2 = no flow; other values = constant head) | integer | n/a | — | — |
| [conn_type](conn_type.md) | Land-to-aquifer connection: 1 = HRU cells, 2 = LSU cells | integer | n/a | — | 1 or 2 |
| [gw_soil](gw_soil.md) | Groundwater to soil transfer (1 = on) | integer | n/a | 0 | 0 or 1 |
| [satx](satx.md) | Saturation-excess groundwater flow to channels (1 = on) | integer | n/a | 0 | 0 or 1 |
| [pumpex](pumpex.md) | Specified pumping from `pumpex.gw` (1 = on) | integer | n/a | 0 | 0 or 1 |
| [tile](tile.md) | Tile drainage from `tile.gw` (1 = on) | integer | n/a | 0 | 0 or 1 |
| [res](res.md) | Reservoir exchange from `rescell.gw` (1 = on) | integer | n/a | 0 | 0 or 1 |
| [wet](wet.md) | Wetland exchange (1 = on) | integer | n/a | 0 | 0 or 1 |
| [fp](fp.md) | Floodplain exchange from `floodplain.gw` (1 = on) | integer | n/a | 0 | 0 or 1 |
| [canal](canal.md) | Canal seepage from `gwflow_canal.con` (1 = on) | integer | n/a | 0 | 0 or 1 |
| [solute](solute.md) | Solute transport from `solute.gw` (1 = on) | integer | n/a | 0 | 0 or 1 |
| [heat](heat.md) | Heat transport (1 = on) | integer | n/a | 0 | 0 or 1 |
| [time_step](time_step.md) | Flow time step | real | day | — | 0 to 1 |
| [write_day](write_day.md) | Daily balance output (1 = on) | integer | n/a | 0 | 0 or 1 |
| [write_mon](write_mon.md) | Monthly balance output (1 = on) | integer | n/a | 0 | 0 or 1 |
| [write_yr](write_yr.md) | Yearly balance output (1 = on) | integer | n/a | 0 | 0 or 1 |
| [write_aa](write_aa.md) | Average annual balance output (1 = on) | integer | n/a | 0 | 0 or 1 |
| [river_thresh](river_thresh.md) | Depth subtracted from every channel-cell bed elevation | real | m | — | — |

## Example

```
codes.gw: GWFlow settings
grid_type ncell cell_size n_rows n_cols bc_type conn_type gw_soil satx pumpex tile res wet fp canal solute heat time_step write_day write_mon write_yr write_aa river_thresh
unstructured 1250 0 0 0 1 1 0 1 0 0 0 0 0 0 0 0 1.0 1 0 1 1 0.0
```

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
