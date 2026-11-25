---
description: "Wetland-bed thickness for groundwater-wetland exchange."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file sets the bed thickness of wetlands for groundwater–wetland exchange. It is read only when GWFlow is on and `wet` is 1 in [codes.gw](../codes.gw/wet.md); wetlands not listed keep a thickness of 0.25 m ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1168-L1169)).

SWAT+ looks for `gwflow.wetland` in the simulation working directory; it is not selected through `file.cio`. See the [`wet_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L73-L97) reader.

# gwflow.wetland

The first two lines are a title and a heading line. Each following line has a wetland name and a thickness. SWAT+ takes the digits in the name as an HRU number (for example `wet019` → 19) and stores the thickness for that HRU; lines whose name has no digits, or whose number is outside 1 to the number of HRUs, are skipped ([`wet_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L83-L94)).

Exchange through the bed follows Darcy's law ([`gwflow_wetland.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L61-L72)):

$$Q = A \, K \, \frac{h - H}{b}$$

where $Q$ is the flow into the wetland (m³/day; negative is seepage to the aquifer), $A$ the wetland area in the cell, $K$ the HRU's wetland conductivity `wet_hc` (converted from mm/hr to m/day), $h$ the head, $H$ the wetland stage and $b$ the bed thickness. The routine looks the thickness up by the HRU's wetland-data number, not by HRU number, so a value reaches the intended wetland only when the two numbers agree ([`gwflow_wetland.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L41)). This is listed in `MODEL_ISSUES.md`.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [wet_name](wet_name.md) | Wetland name ending in the HRU number | string | n/a | — | — |
| [thick_val](thick_val.md) | Wetland-bed thickness | real | m | 0.25 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
