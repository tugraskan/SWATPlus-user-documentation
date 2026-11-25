# Groundwater transit times to channels and tiles

On a structured GWFlow grid, use the same `transit.gw` input described in [Groundwater transit tracks](transit-cell-tracks.md). The reader opens `gwflow_transit_chan` and, if GWFlow tile drainage is enabled, `gwflow_transit_tile`. Both filenames have no extension. Their writes use the transit and tile flags independently of the average-annual water-balance print switch. [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2282), [Final writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2158)

After one descriptive line, each file writes a single row at the end of the simulation. Values are in internal grid-cell order, one for each of the `ncell` starting cells, including inactive and boundary cells. The file has no cell IDs or dates. Values are written in days using `E12.3`. [End-of-simulation gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1980), [Array format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2219)

| File | Value at each starting-cell position |
| --- | --- |
| `gwflow_transit_chan` | Tracker time when the current cell is first flagged as containing a channel |
| `gwflow_transit_tile` | Tracker time when the current cell is first flagged as containing tile drainage |

Both arrays start at zero, and zero remains where the tracker has recorded no hit. A tile hit checks the cell's tile flag. That check does not depend on the cell having positive drain discharge on that day. [Array initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2283), [First-hit tests](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L218)

[Back to GWFlow Outputs](README.md).
