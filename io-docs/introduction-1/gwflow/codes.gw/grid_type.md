---
description: "Grid layout: structured or unstructured"
---

# grid_type

**Code reference:** `grid_type` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L34), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L236)).

Enter `structured` or `unstructured`, in lower case. Several reading steps compare the text exactly, and a cell's channel connections are set only for these two values ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L644-L648)).

With `grid_type` = `structured`, SWAT+ maps cell numbers through an identity list, so structured and unstructured grids both use cell numbers 1 to `ncell` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L313-L319)). The choice changes how some optional files are laid out: with `structured`, the tile flags in [tile.gw](../tile.gw/README.md), the mineral values in [minerals.gw](../minerals.gw/README.md) and the reaction-group arrays of `solute.gw` are read as `n_rows` lines of `n_cols` values, and [transit.gw](../transit.gw/README.md) is read only for this layout. Those row-by-column readers use arrays that are never allocated in this source, so the structured layout of those files cannot be read ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1063-L1073)). This is listed in `MODEL_ISSUES.md`.
