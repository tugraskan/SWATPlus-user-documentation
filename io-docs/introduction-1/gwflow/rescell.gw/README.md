---
description: "Reservoir-bed properties and the cells occupied by each reservoir."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file marks the cells covered by each reservoir and sets the reservoir-bed properties. It is read only when `res` is 1 in [codes.gw](../codes.gw/res.md).

SWAT+ looks for `rescell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1109-L1157) reader.

# rescell.gw

Each item is on its own line, in this order: a title line, a heading line, `res_thick`, `res_K`, `num_res_cells`, a heading line, then `num_res_cells` lines of `res_cell res_id res_stage` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1113-L1157)). Lines with `res_id` 0 are skipped.

Each day, every active neighbor (from `cellcon.gw`) of a reservoir cell exchanges water with the reservoir ([`gwflow_reservoir.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L44-L81)):

$$Q = K \, \frac{z_{r} - h}{b} \, b \, L = K \, (z_{r} - h) \, L$$

where:
- $Q$ is the flow into the aquifer ($\text{m}^3/\text{day}$),
- $K$ is `res_K` (`m/day`),
- $b$ is `res_thick` (m),
- $h$ is the neighbor's head (m),
- $L$ is the connection width between the two cells ($\sqrt{\min(A)}$, m), and
- $z_{r}$ is the ground elevation of the reservoir cell from `cells.gw` (m).

The thickness cancels, and neither `res_stage` nor the reservoir's water level is used. These are listed in `MODEL_ISSUES.md`. Seepage is set to 0 when it would exceed the reservoir volume.

## Bed properties

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [res_thick](res_thick.md) | Reservoir-bed thickness | real | m | — | — |
| [res_K](res_k.md) | Reservoir-bed hydraulic conductivity | real | m/day | — | — |

## Connections

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num_res_cells](num_res_cells.md) | Number of connection lines | integer | n/a | — | — |
| [res_cell](res_cell.md) | Cell covered by the reservoir | integer | n/a | — | 1 to ncell |
| [res_id](res_id.md) | Reservoir number | integer | n/a | — | 0 to number of reservoirs |
| [res_stage](res_stage.md) | Reservoir stage; not used | real | m | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
