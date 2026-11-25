# Groundwater transit tracks

On a structured GWFlow grid, place `transit.gw` in the model run directory. The reader skips two header records, reads the number of selected cells, then reads one starting cell ID per record. It maps the IDs through `cell_id_list` and preserves their input order. This file is enabled by `transit.gw`, with no separate `print.prt` switch. The model writes `gwflow_transit_cell` without a filename extension. [Configuration and file opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2247)

After six descriptive lines, each row has four values per selected starting cell in input order. The writer uses fixed-width numeric fields (`F20.4`), including for the current cell index. [Tracking row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L236)

| Position within each group | Value | Unit |
| --- | --- | --- |
| 1 | Cumulative tracker time (`t`) | days |
| 2 | Tracked x coordinate (`x`) | m |
| 3 | Tracked y coordinate (`y`) | m |
| 4 | Current internal grid cell index (`cell`) | — |

The tracker starts at each cell centroid. Its update and row write run once after the lateral solver's loop over flow substeps. Each update increments `t` by one `gw_time_step`, so the recorded time advances by that configured step even when the solver takes multiple substeps between rows. The row has no calendar date or repeated starting-cell IDs. [Initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2252), [Flow substeps and tracker update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L173)

See [channel and tile transit times](transit-channel-tile-times.md) for the final per-cell results.

[Back to GWFlow Outputs](README.md).
