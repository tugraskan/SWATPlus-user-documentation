---
description: "Recall temporal type code in pest.com"
---

# typ

**Code reference:** `rec_pest(i)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L281), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L232)).

Integer recall temporal type (`0` by default) selecting allocation of `rec_pest(i)%hd_pest` in [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L242-L250): `1` for daily (`366 x nbyr`), `2` for monthly (`12 x nbyr`), or `3` for yearly (`1 x nbyr`). Note that `rec_pest%hd_pest` is not populated or used in SWAT+ main (`6f515368`).
