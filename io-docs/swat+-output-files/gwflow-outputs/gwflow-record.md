# GWFlow diagnostic log

Request GWFlow by setting `gwflow = 1` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). During basin object setup, SWAT+ checks for `chancell.gw` and opens `gwflow_record` without a filename extension. The opener runs even when the missing-file branch turns GWFlow off. A file containing only the opening title confirms that setup reached the opener. [Activation check and opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L45), [GWFlow input calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L186)

The log has no separate `print.prt` switch or fixed table layout. It contains startup messages, diagnostics from the input readers, and one line of the form `gwflow subroutine called: YEAR JDAY` per call to the GWFlow simulator. `YEAR` is the calendar year and `JDAY` is the day of year. The line is written at entry to the simulator, before the groundwater calculations and balance-file writes. [End of initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2367), [Simulator log entry](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L62)

Some messages retain older filenames. For these messages, use the input names in the right column. [Codes reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L203), [Connection checks](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L327), [Grid inputs](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L369), [Output configuration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L570)

| Name in the log | Input used by this revision |
| --- | --- |
| `gwflow.input` or `gwflow.codes` | `codes.gw` for the basic options and water-balance output flags |
| `gwflow.hrucell` | `hrucell.gw` |
| `gwflow.lsucell` | `lsucell.gw` |
| `gwflow.zones` | `zones.gw` |
| `gwflow.cells` | `cells.gw` |
| `gwflow.cellcons` | `cellcon.gw` |
| `gwflow.outputs` | `outputs.gw` |

When the log says `print.prt gwflow_wb overrides gwflow.input flags`, the flags being overridden come from `codes.gw`. The message appears when the named `gwflow_wb` row was read. See [GWFlow Basin Water Balance](../gwflow-basin-water-balance/README.md) for the reporting settings. [Override code](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L263)

[Back to GWFlow Outputs](README.md).
