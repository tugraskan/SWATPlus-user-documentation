---
description: "Lateral soil flow including shallow groundwater discharge for HRU-LTEs"
---

# latq

**Code reference:** `bwb_d%latq` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L10)).

The full-HRU record uses `latq(j)` after the subsurface lag calculation. HRU-LTE reports `flowlat + hlt(isd)%gwflow`, so its value includes shallow groundwater discharge. [subsurface lag](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_substor.f90#L51-L73), [full HRU](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L731-L737), [HRU-LTE](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L368-L375).

**Unit:** mm.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
