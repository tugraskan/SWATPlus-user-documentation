---
description: "This file specifies the number of soil layers included in carbon-layer output."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies the number of soil layers included in carbon-layer output.

SWAT+ looks for `carbon_layers.prt` in the simulation working directory; it is not selected through `file.cio`. See [`carbon_layers_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_layers_read.f90#L29-L46) for reading and validation, and [`output_landscape_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L26-L32) for the automatic default when the file is absent.

# carbon_layers.prt

After the title and column headings, enter the number of soil layers to include in carbon-layer output.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [n_lyr](n_lyr.md) | Count of carbon soil layers to be read for the simulation | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
