# Configured GWFlow Exchange and Observation Matrices

These daily files start with a title line. Each data write begins with `jday, mon, day, yr`, followed by one value for each configured group or flagged channel-cell connection. The grouping and observation files determine the number and order of values. The output writes no group IDs or cell IDs. [Daily writers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L225-L257).

| File | Configured value block |
| --- | --- |
| `gwflow_gwsw_group_day.txt` | One signed `gwsw + swgw` volume (m³) summed over the listed cells in each group |
| `gwflow_chan_obs_flow_day.txt` | One `gwsw + swgw + satx` volume (m³) for the cell on each flagged connection |
| `gwflow_chan_obs_no3_day.txt` | One signed NO3 mass (g), summing the same three processes for the cell on each flagged connection |

## How to produce these files

Enable GWFlow and its `gwflow_flux` diagnostic switch. A named `gwflow_flux` row in `print.prt` enables the switch with `y` in either the daily or yearly column. The switch defaults to on when the row is absent. The matrices always report daily values. The nitrate file also requires `solute = 1` in `codes.gw`. [Print switch and solute setting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L246-L310), [default switch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L26).

- **Exchange groups.** Add `sw_group.gw` with a metadata line and a column header, then one whitespace-delimited `group_id ncell cell_id ...` line per group. Use consecutive group lines and up to 38 cell IDs per line. The reader uses the line order and ignores the `group_id` value. It counts a cell once for each occurrence in a group. [Group reader and opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2302-L2344), [field buffer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L184-L185).
- **Channel observations.** Set `obs` to a positive integer in column 7 of a `chancell.gw` connection row. Column 6 is the depth-zone field. Flagged rows supply columns in file order, regardless of the positive `obs` value. Each column reads the cell's combined diagnostics across connections. If two flagged connections refer to the same cell, both columns contain that cell's value. [Observation flag reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L48-L82), [cell list and openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L660-L678).

## Interpreting the values

The sign is from the aquifer's perspective. Groundwater discharge (`gwsw`) and saturation excess (`satx`) are negative, and channel leakage into groundwater (`swgw`) is positive. These are net daily exchanges. A zero sum can result from opposing flows, and the observation flow includes saturation excess that is absent from the exchange-group sum. [Channel exchange](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L74-L108), [saturation-excess sign](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L45-L59).

The daily water `gwsw` and `swgw` values accumulate within each direction. The corresponding daily nitrate values, as well as the water and nitrate `satx` values, are replaced on each qualifying call. If several connections write the same cell and term on one day, the matrix uses the last stored value for that term. An observed nitrate mass can omit earlier transfers that the daily water exchange includes. [Discharge mass assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L148-L160), [leakage mass assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L237-L244), [saturation-excess mass assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L90-L104).

[Back to the GWFlow Outputs index](README.md).
