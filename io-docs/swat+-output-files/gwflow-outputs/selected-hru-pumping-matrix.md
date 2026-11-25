# Selected-HRU Pumping Matrix

`gwflow_cell_wb_ppag_obs_day.txt` has a source payload of `year, jday, pumping_for_each_selected_HRU`, in the order actually read from `hru_pump.gw`. It requires the [`gwflow_pump` switch](README.md#defaults-when-a-print-row-is-absent) to be on and the selected HRUs in `hru_pump.gw`. The banner still refers to the obsolete `gwflow.hru_pump_observe` name.

This write occurs before the daily pumping reset. However, its format `119` expects three integers before the real pumping values, while the payload supplies only two integers. The first real value therefore encounters an integer descriptor; successful matrix serialization is not established by the title or write-list width ([actual configuration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L930); [payload](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L115); [format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L583)).

The input reader skips one line, reads the selection count, and then reads one internal HRU index per row. At output time those indices address the pumping array directly, without GIS-ID conversion or a bounds check. Repeated indices duplicate the same value. [Selection reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L930-L941), [Array lookup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L115-L120)

[Back to the GWFlow Outputs index](README.md).
