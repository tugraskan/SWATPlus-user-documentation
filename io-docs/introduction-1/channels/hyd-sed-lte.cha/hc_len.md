---
description: Fraction of phosphorus in channel bank and bed that is bioavailable
---

# p\_bio

**Code reference:** `sd_chd(idb)%p_bio` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L41)).

This fraction (default `0.30`) splits phosphorus associated with eroded bank sediment between particulate and soluble forms in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L242-L244) (`solp` receives `p_bio`, and `sedp` receives `1 - p_bio`).
