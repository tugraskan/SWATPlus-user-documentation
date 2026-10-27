---
description: >-
  This file specifies the land area and the total area (including ponds and
  reservoirs) of the watershed and the counts of all spatial objects in a
  simulation.
---

# object.cnt

| Field     | Description                                                | Type    |
| --------- | ---------------------------------------------------------- | ------- |
| name | Name of the watershed | string |
| ls\_area\* | Land area of the watershed in ha                           | real    |
| tot\_area\* | Total area of the watershed in ha                          | real    |
| obj\* | Total number of spatial objects in the simulation. When GWFlow is active and the input `gwfl` count is zero, SWAT+ adds the river cells read from `chancell.gw` and removes the aquifer count. | integer |
| hru       | Number of HRUs in the simulation                           | integer |
| lhru\* | Number of HRU-ltes in the simulation                       | integer |
| rtu\* | Number of routing units in the simulation                  | integer |
| gwfl\* | Number of GWFlow river cells. When GWFlow is active and this input is zero, SWAT+ replaces it with the number of river cells in `chancell.gw`. Editor-generated examples may label this positional column `mfl`. | integer |
| aqu | Number of aquifers in the simulation. When GWFlow is active and `chancell.gw` is present, SWAT+ sets this count to zero and disables the aquifer connection file. | integer |
| cha\* | Number of channels in the simulation | integer |
| res       | Number of reservoirs in the simulation                     | integer |
| rec\* | Number of recalls (point sources/inlets) in the simulation | integer |
| exco      | Number of export coefficients in the simulation            | integer |
| dlr\* | Number of delivery ratios in the simulation                | integer |
| can\* | Number of canals in the simulation | integer |
| pmp\* | Number of pumps in the simulation | integer |
| out\* | Number of outlets in the simulation                        | integer |
| lcha\* | Number of SWAT-DEG channels in the simulation | integer |
| aqu2d     | Currently not used                                         | integer |
| hrd\* | Currently not used                                         | integer |
| wro       | Currently not used                                         | integer |

\* Input-file labels marked with an asterisk have different Fortran names: `ls_area` → `bsn%area_ls_ha`; `tot_area` → `bsn%area_tot_ha`; `obj` → `sp_ob%objs`; `lhru` → `sp_ob%hru_lte`; `rtu` → `sp_ob%ru`; `gwfl` → `sp_ob%gwflow`; `cha` → `sp_ob%chan`; `rec` → `sp_ob%recall`; `dlr` → `sp_ob%dr`; `can` → `sp_ob%canal`; `pmp` → `sp_ob%pump`; `out` → `sp_ob%outlet`; `lcha` → `sp_ob%chandeg`; `hrd` → `sp_ob%herd`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_objs.f90#L38).
