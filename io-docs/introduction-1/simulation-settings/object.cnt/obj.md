---
description: Total number of spatial objects in the simulation
---

# obj

**Code reference:** `sp_ob%objs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L441)).

Total number of spatial objects in the simulation (integer; Fortran struct default: `0`). After reading `object.cnt` in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L91-L95), SWAT+ allocates the global object arrays `ob`, `obcs`, `obcs_alloc`, and `obom` to size `obj`.

When GWFlow is active (`gwflow = 1` in `codes.bsn`), `chancell.gw` exists, and the input `gwfl` count is `0`, [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L68) updates the total object count before allocating those arrays:

$$N_{\text{objs}} = N_{\text{objs,in}} + N_{\text{riv}} - N_{\text{aqu}}$$

where $N_{\text{riv}}$ is the number of river cells read from `chancell.gw` and $N_{\text{aqu}}$ is the input `aqu` count.
