---
description: Groundwater flow module input documentation
---

# GWFlow

GWFlow replaces the SWAT+ aquifer objects with a grid of groundwater cells. It runs when `gwflow` is 1 in [codes.bsn](basin-1/codes.bsn/gwflow.md) and [chancell.gw](gwflow/chancell.gw/README.md) is present; the aquifer objects are then turned off ([`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L45-L68)). None of these files is named in `file.cio`: SWAT+ looks for them by fixed name in the simulation folder ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L222-L526)).

Required files:

- [codes.gw](gwflow/codes.gw/README.md): settings and process switches
- [zones.gw](gwflow/zones.gw/README.md): aquifer, streambed and thermal properties by zone
- [cells.gw](gwflow/cells.gw/README.md): cell geometry, status, zones and initial heads
- [cellcon.gw](gwflow/cellcon.gw/README.md): neighboring cells
- [chancell.gw](gwflow/chancell.gw/README.md): channel–cell connections
- [outputs.gw](gwflow/outputs.gw/README.md): observation cells
- [hrucell.gw](gwflow/hrucell.gw/README.md) or [lsucell.gw](gwflow/lsucell.gw/README.md): land-unit–cell connections

Files read when the matching `codes.gw` setting is 1:

- [pumpex.gw](gwflow/pumpex.gw/README.md) (`pumpex`)
- [tile.gw](gwflow/tile.gw/README.md) (`tile`)
- [rescell.gw](gwflow/rescell.gw/README.md) (`res`)
- [gwflow.wetland](gwflow/gwflow.wetland/README.md) (`wet`)
- [floodplain.gw](gwflow/floodplain.gw/README.md) (`fp`)
- [gwflow_canal.con](databases/gwflow_canal.con/README.md) (`canal`)
- [solute.gw](gwflow/solute.gw/README.md), [cell_sol.gw](gwflow/cell_sol.gw/README.md) and [minerals.gw](gwflow/minerals.gw/README.md) (`solute`)

Files used whenever they are present:

- [chan_depth.gw](gwflow/chan_depth.gw/README.md): daily channel depths
- [phreato.gw](gwflow/phreato.gw/README.md) and [phreato_cell.gw](gwflow/phreato_cell.gw/README.md): phreatophyte uptake
- [ponds.gw](gwflow/ponds.gw/README.md), [pond_cell.gw](gwflow/pond_cell.gw/README.md) and [pond_div.gw](gwflow/pond_div.gw/README.md): recharge ponds
- [tvheads.gw](gwflow/tvheads.gw/README.md): yearly boundary heads (read but not used)

Output-only files, which do not change the simulation:

- [hru_pump.gw](gwflow/hru_pump.gw/README.md): HRU irrigation pumping
- [sw_group.gw](gwflow/sw_group.gw/README.md): groundwater–channel exchange by cell group
- [gwflow.wbgroups](gwflow/gwflow.wbgroups/README.md): water balance by cell group
- [transit.gw](gwflow/transit.gw/README.md): groundwater travel paths (structured grids only)

Messages about missing or inconsistent files go to the [GWFlow record file](../swat+-output-files/gwflow-outputs/gwflow-record.md), `gwflow_record` ([`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L85)).
