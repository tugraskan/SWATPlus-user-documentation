---
description: "This file supplies constituent settling, reaction, and initial-concentration parameters for reservoirs and wetlands."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies settling velocities, first-order degradation rates, temperature adjustments, and initial concentrations for selenate (`seo4`), selenite (`seo3`), and boron (`born`) in reservoirs and wetlands.

SWAT+ looks for `cs_res` in the simulation working directory; it is not selected through `file.cio`. It reads this file via [`res_read_csdb.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_csdb.f90#L24-L68) only when `cs_res` exists and `nut_res` in `file.cio` is not `null`. Before data rows, SWAT+ skips **15 header lines** (2 title lines, 12 descriptive lines, and 1 column-header line).

# cs\_res

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the reservoir and wetland constituent record | string | n/a | — | — |
| [v\_seo4](v_seo4.md) | Settling velocity for selenate | real | m/day | 0.001 | — |
| [v\_seo3](v_seo3.md) | Settling velocity for selenite | real | m/day | 0.001 | — |
| [v\_born](v_born.md) | Settling velocity for boron | real | m/day | 0.001 | — |
| [k\_seo4](k_seo4.md) | First-order degradation constant for selenate at 20 °C | real | 1/day | 0.05 | — |
| [k\_seo3](k_seo3.md) | First-order degradation constant for selenite at 20 °C | real | 1/day | 0.03 | — |
| [k\_born](k_born.md) | First-order degradation constant for boron at 20 °C | real | 1/day | 0.00 | — |
| [theta\_seo4](theta_seo4.md) | Temperature adjustment factor for selenate degradation | real | n/a | 1.08 | — |
| [theta\_seo3](theta_seo3.md) | Temperature adjustment factor for selenite degradation | real | n/a | 1.08 | — |
| [theta\_born](theta_born.md) | Temperature adjustment factor for boron degradation | real | n/a | 1.08 | — |
| [c\_seo4](c_seo4.md) | Initial concentration of selenate | real | g/m3 | 0.0 | — |
| [c\_seo3](c_seo3.md) | Initial concentration of selenite | real | g/m3 | 0.0 | — |
| [c\_born](c_born.md) | Initial concentration of boron | real | g/m3 | 0.0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
