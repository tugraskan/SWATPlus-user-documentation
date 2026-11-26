# Basin Sediment Budget

In [`print.prt`](../../introduction-1/simulation-settings/print.prt/README.md), enable the desired periods on `channel_sd` and set `csvout = y` for CSV copies. The files are `sedbud_day`, `sedbud_mon`, `sedbud_yr`, and `sedbud_aa` with `.txt` or `.csv` extensions. They are opened only when there is at least one SWAT-DEG channel, and data rows begin after `nyskip`. The daily file writes on every eligible simulation day when enabled. [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L415-L478), [report calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441-L450), [daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sedbud_output.f90#L8-L19).

{% hint style="warning" %}
On SWAT+ dev the basin writer is called even when there are no SWAT-DEG channels, so with `channel_sd` switched on it writes to units that were never opened (with gfortran this creates files named `fort.3152` and similar). This comes from source reading.
{% endhint %}

Each row has four date fields and six sediment terms. Monthly and yearly rows sum the daily terms. Average annual divides the sum of the yearly terms by `time%yrs_prt`. If the simulation stops before month end, the remaining monthly values are included in yearly and average-annual totals. [Period writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sedbud_output.f90#L22-L72).

| Field | Description | Unit |
| --- | --- | --- |
| `jday` | Day of year | n/a |
| `mon` | Month | n/a |
| `day` | Day of month | n/a |
| `yr` | Calendar year | n/a |
| `upland_t` | Sum of routed sediment yield from full HRUs | tons |
| `ebank_t` | Bank erosion from SWAT-DEG channels | tons |
| `ebtm_t` | Calculated gross bed erosion from SWAT-DEG channels | tons |
| `fp_t` | Floodplain deposition from SWAT-DEG channels | tons |
| `res_dep_t` | Reservoir sediment inflow minus outflow, summed across reservoirs | tons |
| `wet_dep_t` | Wetland sediment inflow minus outflow, summed across wetlands | tons |

## What the totals include

- **Full-HRU sediment yield.** The model adds `sedyld` after surface routing and lagging. This is a whole-HRU mass in tons, and it can include sediment routed in from elsewhere. HRU-LTE generates its own sediment hydrograph but does not add directly to `upland_t`. [Full-HRU surface routing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L319-L324), [surface lagging](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L599-L603), [basin accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L871-L883), [HRU-LTE hydrograph](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L429-L432).
- **Wetland flushing.** The flush branch sets both `sedyld` and `ht2%sed` to the calculated release mass. The subsequent yield assignment adds the two with `bypass = 1`. The HRU therefore starts its subsequent surface routing with twice the flush mass, while the wetland report's outflow record carries the single release mass. Basin `upland_t` uses the HRU yield after routing. [Wetland flush and yield assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L227-L255), [wetland report records](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L270-L278).
- **Channel erosion and deposition.** The channel calculation adds bank erosion and subtracts channel-bed deposition in the routed hydrograph. The basin table has a floodplain deposition column, and it omits the separate channel-bed deposition term. `ebtm_t` is gross bed erosion, also written by the [channel erosion report](channel-erosion-by-channel.md). The addition of bed erosion to the routed hydrograph is commented out. [Channel routing changes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L238-L296), [basin assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L304-L322).
- **Reservoir and wetland differences.** These columns subtract routed sediment outflow from routed sediment inflow. Positive values indicate more sediment entered than left, and negative values indicate the reverse. They can reflect changes in storage as well as deposition or release. [Reservoir contribution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L252-L257), [wetland contribution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L270-L279).

The table has no outlet-export, change-in-storage, or balance-residual column. The six terms do not form a closed basin sediment balance. [Output record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L272-L281), [outlet hydrograph assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L368-L369).


[Back to the Channel Sediment Budgets index](README.md).
