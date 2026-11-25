---
description: >-
  This file specifies the land area and the total area (including ponds and
  reservoirs) of the watershed and the counts of all spatial objects in a
  simulation.
---

# object.cnt

This file is read by [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the watershed | string |  |  |  |
| [ls\_area](ls_area.md) | Land area of the watershed in ha | real | ha |  |  |
| [tot\_area](tot_area.md) | Total area of the watershed in ha | real | ha |  |  |
| [obj](obj.md) | Total number of spatial objects in the simulation. When GWFlow is active and the input `gwfl` count is zero, SWAT+ adds the river cells read from `chancell.gw` and removes the aquifer count. | integer |  |  |  |
| [hru](hru.md) | Number of HRUs in the simulation | integer |  |  |  |
| [lhru](lhru.md) | Number of HRU-ltes in the simulation | integer |  |  |  |
| [rtu](rtu.md) | Number of routing units in the simulation | integer |  |  |  |
| [gwfl](gwfl.md) | Number of GWFlow river cells. When GWFlow is active and this input is zero, SWAT+ replaces it with the number of river cells in `chancell.gw`. Editor-generated examples may label this positional column `mfl`. | integer |  |  |  |
| [aqu](aqu.md) | Number of aquifers in the simulation. When GWFlow is active and `chancell.gw` is present, SWAT+ sets this count to zero and disables the aquifer connection file. | integer |  |  |  |
| [cha](cha.md) | Number of channels in the simulation | integer |  |  |  |
| [res](res.md) | Number of reservoirs in the simulation | integer |  |  |  |
| [rec](rec.md) | Number of recalls (point sources/inlets) in the simulation | integer |  |  |  |
| [exco](exco.md) | Number of export coefficients in the simulation | integer |  |  |  |
| [dlr](dlr.md) | Number of delivery ratios in the simulation | integer |  |  |  |
| [can](can.md) | Number of canals in the simulation | integer |  |  |  |
| [pmp](pmp.md) | Number of pumps in the simulation | integer |  |  |  |
| [out](out.md) | Number of outlets in the simulation | integer |  |  |  |
| [lcha](lcha.md) | Number of SWAT-DEG channels in the simulation | integer |  |  |  |
| [aqu2d](aqu2d.md) | Currently not used | integer |  |  |  |
| [hrd](hrd.md) | Currently not used | integer |  |  |  |
| [wro](wro.md) | Currently not used | integer |  |  |  |
