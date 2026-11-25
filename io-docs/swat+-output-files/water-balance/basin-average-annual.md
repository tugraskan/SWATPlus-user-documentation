# Basin average-annual water balance

Set the average-annual column of `basin_wb` to `y` in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) to create `basin_wb_aa.txt`. Set `csvout` to `y` for `basin_wb_aa.csv`. Both formats write a basin row at the end of the simulation when basin output is called. Both basin identifiers are `1`. [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L1054), [Basin output caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L632), [Annual writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L203)

The first 49 values follow the [common water-balance table](README.md). The last two are calibration information. The shared header labels these positions `plant_cov` and `mgt_ops`, and the units record ends at position 49. [Shared headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L252), [Basin data writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L214)

| Position | Printed heading | Value written |
| --- | --- | --- |
| 50 | `plant_cov` | Simulation or calibration label (`cal_sim`) |
| 51 | `mgt_ops` | Calibration adjustment value (`cal_adj`) |

If the run ends mid-month, the last partial month stays outside the annual accumulators. The final soil-water and snow values still come from the last simulated day. [Basin month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L100-L111), [final state assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L203-L218).

The initial label is `Original Simulation` and the initial adjustment is zero. Calibration code can change these values. The adjustment's meaning depends on the calibration path. [Initial values](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L6), [Example adjustment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L110)

Flux sums divide by `time%yrs_prt`. The accumulated curve number and the four mean storage fields divide by `time%days_prt`. The writer restores the initial soil-water and snow stores from the annual record and takes their final values from the last daily basin record. [Annual calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L203)
