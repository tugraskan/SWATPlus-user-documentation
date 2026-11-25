---
description: "HRUs whose daily groundwater irrigation pumping is written to output."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file selects HRUs whose daily groundwater pumping for irrigation is written to `gwflow_cell_wb_ppag_obs_day.txt`. It does not change the simulation.

SWAT+ looks for `hru_pump.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L930-L948) reader.

# hru_pump.gw

The file has one title line (no column-heading line), the number of HRUs, then one HRU number per line ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L934-L939)).

## HRU count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num_hru_pump_obs](num_hru_pump_obs.md) | Number of HRUs listed | integer | n/a | — | — |

## HRU numbers

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [hru_pump_ids(i)](hru_pump_ids_i.md) | HRU number, one per line | integer | n/a | — | 1 to number of HRUs |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
