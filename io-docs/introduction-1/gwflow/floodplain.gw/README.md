---
description: "Cells under each channel's floodplain and their exchange properties."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the cells under each channel's floodplain. It is read only when `fp` is 1 in [codes.gw](../codes.gw/fp.md).

SWAT+ looks for `floodplain.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1180-L1225) reader.

# floodplain.gw

The file has a title line, the number of cells, a heading line, then one line per cell: `gw_fp_cellid gw_fp_chanid gw_fp_K gw_fp_area` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1181-L1192)).

Exchange happens only on days when the channel's peak flow exceeds bankfull flow ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L112-L117)). Each active cell then exchanges water with the channel under a unit hydraulic gradient ([`gwflow_floodplain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_floodplain.f90#L53-L92)):

$$Q = \pm K \, A$$

where $Q$ is in m³/day, $K$ is `gw_fp_K` and $A$ the area. The flow is out of the aquifer when the head is above the cell's ground elevation plus the channel depth, and into the aquifer otherwise. It is limited to the water available in the cell or the channel.

## Cell count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_fp_ncells](gw_fp_ncells.md) | Number of floodplain cell lines | integer | n/a | — | — |

## Floodplain cells

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_fp_cellid](gw_fp_cellid.md) | Cell number | integer | n/a | — | 1 to ncell |
| [gw_fp_chanid](gw_fp_chanid.md) | Channel whose floodplain covers the cell | integer | n/a | — | — |
| [gw_fp_K](gw_fp_k.md) | Floodplain-bed hydraulic conductivity | real | m/day | — | — |
| [gw_fp_area](gw_fp_area.md) | Floodplain area in the cell | real | m² | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
