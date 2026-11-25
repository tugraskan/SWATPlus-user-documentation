# Spatial Objects

Each active spatial object in SWAT+ is counted in [`object.cnt`](../../introduction-1/simulation-settings/object.cnt/README.md), wired into the routing network through a corresponding connect file ([`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L127-L191)), and executed in command order ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L276)). Landscape Units (LSUs) are grouping units rather than routed `object.cnt` objects.

| Spatial Object | `object.cnt` Column | Receiver Code (`obj_typ`) | Connect File | Input Documentation |
| --- | --- | --- | --- | --- |
| HRU | `hru` | `hru` | `hru.con` | [`hru-data.hru`](../../introduction-1/hydrologic-response-units/hru-data.hru/README.md) |
| HRU-LTE | `lhru` | `hlt` | `hru-lte.con` | [`hru-lte.hru`](../../introduction-1/hydrologic-response-units/hru-lte.hru/README.md) |
| Routing Unit | `rtu` | `ru` | `rout_unit.con` | [Routing Units](../../introduction-1/routing-units/README.md) |
| Aquifer | `aqu` | `aqu` | `aquifer.con` | [Aquifers](../../introduction-1/aquifers/README.md) |
| GWFlow River Cell | `gwfl` | *(none — cannot be targeted via `obj_typ`)* | `gwflow.con` | [GWFlow](../../introduction-1/modflow.md) |
| SWAT-DEG Channel | `lcha` | `sdc` | `chandeg.con` | [Channels](../../introduction-1/channels/README.md) |
| Reservoir / Pond | `res` | `res` | `reservoir.con` | [Reservoirs and Ponds](../../introduction-1/reservoirs/README.md) |
| Point Source / Inlet | `rec` | *(none — cannot receive routed inflows)* | `recall.con` | [Point Sources and Inlets](../../introduction-1/point-sources-and-inlets/README.md) |
| Export Coefficient | `exco` | `exc` | `exco.con` | [Point Sources and Inlets](../../introduction-1/point-sources-and-inlets/README.md) |
| Delivery Ratio | `dlr` | `dr` | `delratio.con` | [`delratio.del`](../../introduction-1/routing-units/delratio.del/README.md) |
| Outlet | `out` | `out` | `outlet.con` | [Connectivity](../../introduction-1/connectivity/README.md) |
| Landscape Unit | *(none)* | *(none — not a routed object)* | *(none)* | [Landscape Units](../../introduction-1/landscape-units/README.md) |

## Hydrologic Response Unit (HRU and HRU-LTE)

Hydrologic Response Units (`hru`) are the core land-phase simulation units, executed by [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L280) (`hru_control`). An HRU simulates soil water, plant growth, management operations, erosion, and nutrient/constituent cycling, and can route five hydrograph components (`tot`, `sur`, `lat`, `til`, and `rhg`). Wetlands are simulated on ponded HRUs when `surf_stor` links to [`wetland.wet`](../../introduction-1/wetlands/README.md) ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L338)).

HRU-LTEs (`hru_lte`, receiver code `hlt`), executed at [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L285) (`hru_lte_control`), provide a simplified lumped land-unit representation with fewer soil and management inputs and output a single `tot` hydrograph.

## Landscape Unit (LSU)

A Landscape Unit is a collection of HRUs and/or HRU-LTEs that can represent a subbasin, an upland or floodplain zone, or a multi-HRU grid cell. LSUs are not listed in `object.cnt` and are not routed via a connect file; instead, membership and area weights (`bsn_frac` and `ru_frac`) are read from [`ls_unit.ele`](../../introduction-1/landscape-units/ls_unit.ele/README.md) and [`ls_unit.def`](../../introduction-1/landscape-units/ls_unit.def/README.md) in [`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L1-L138).

In SWAT+ main (`6f515368`), LSUs primarily aggregate landscape outputs at LSU and basin scales ([`lsu_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L32-L50), [`basin_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L29-L49)), and are also referenced in landscape soft calibration ([`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L108)), HRU area-fraction updates ([`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L94-L97)), and GWFlow recharge and groundwater-ET loops ([`gwflow_rech.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_rech.f90#L71-L78), [`gwflow_gwet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_gwet.f90#L36-L40)).

## Routing Unit (RU)

A Routing Unit lumps outflows from multiple elements—such as all HRUs in a subbasin, a set of representative hillslope zones, or tile flow from multiple fields—and routes the combined flow components (`tot`, `sur`, `lat`, `til`, and `rhg`) via `rout_unit.con` to channels, aquifers, HRUs/wetlands, or other objects. Routing Units are configured through [`rout_unit.rtu`](../../introduction-1/routing-units/untitled/README.md), [`rout_unit.def`](../../introduction-1/routing-units/untitled-1/README.md), and [`rout_unit.ele`](../../introduction-1/routing-units/untitled-2/README.md).

Element mapping in [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L143-L162) accepts `hru`, `hlt`, `ru`, `cha`, `res`, `exc`, `dr`, `out`, and `sdc`. Each day, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L290) calls [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L82-L115), which aggregates member element hydrographs weighted by area fraction (`frac`) and delivery ratio (`dlr`).

## Aquifer and GWFlow

An Aquifer (`aqu`, [Aquifers](../../introduction-1/aquifers/README.md)) is a lumped 1-D groundwater storage object executed at [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L302) (`aqu_1d_control`). It receives recharge (`rhg`) from landscape objects and routes groundwater return flow (`tot`) and deep seepage (`rhg`) via `aquifer.con`, with optional multi-channel return-flow distribution via [`aqu_cha.lin`](../../introduction-1/connectivity/aqu_cha.lin.md).

When the gridded 2-D [GWFlow](../../introduction-1/modflow.md) module is active (`gwflow = 1` in `codes.bsn` with `chancell.gw` present), [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L46-L75) replaces `aqu` objects with `gwflow` river-cell objects (`gwflow.con`), which are simulated in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L294) (`gwflow_simulate`).

## Channel

Active stream channels in SWAT+ main (`6f515368`) are SWAT-DEG channels (`chandeg`, receiver code `sdc`, `chandeg.con`; see [Channels](../../introduction-1/channels/README.md)), executed at [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L378) (`sd_channel_control3`). Channels route streamflow (`tot`) and can link to floodplain HRUs or objects through [`chan-surf.lin`](../../introduction-1/connectivity/chan_surf.lin.md).

Legacy SWAT channels (`chan`, receiver code `cha`, `channel.con`) are still read in [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L150-L153), but they have no dispatch case in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L276).

## Reservoir (and Pond)

Reservoir objects (`res`, [Reservoirs and Ponds](../../introduction-1/reservoirs/README.md)) represent both on-network reservoirs and off-network or connected ponds. Executed at [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L315) (`res_control`), they balance storage, precipitation, evaporation, seepage, and decision-table or weir releases, and send `tot` outflow via `reservoir.con`.

## Recall, Export Coefficient, Delivery Ratio, and Outlet

* **Recall (`recall`):** Supplies external time-series point-source or inlet loadings ([Point Sources and Inlets](../../introduction-1/point-sources-and-inlets/README.md)), executed at [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L331) (`recall_nut`); cannot act as a receiving object.
* **Export Coefficient (`exco` / `exc`):** Supplies static constant loadings loaded at startup in [`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L79-L87); its outgoing hydrograph comes from the database record rather than modifying incoming flows.
* **Delivery Ratio (`dr`):** Standalone scaling object ([`delratio.del`](../../introduction-1/routing-units/delratio.del/README.md)) executed at [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L365) (`constit_hyd_mult`) that multiplies incoming water, sediment, nutrient, and constituent loads by user-specified ratios.
* **Outlet (`outlet` / `out`):** Watershed or sub-network collection point handled in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L276) that sums incoming `tot` hydrographs.

## Reserved and Unused `object.cnt` Slots

[`object.cnt`](../../introduction-1/simulation-settings/object.cnt/README.md) also includes columns for `can` and `pmp`, which only reserve object-index offsets in [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L105-L112) without connection files or simulation dispatch, as well as `aqu2d`, `hrd`, and `wro`, which are parsed in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38) and unused in SWAT+ main (`6f515368`). Managed canals, pumping, and water-allocation transfers are configured via [Water Allocation](../../introduction-1/water-allocation/README.md).
