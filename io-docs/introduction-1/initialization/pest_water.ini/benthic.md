---
description: Initial pesticide values for benthic sediment
---

# benthic

**Code reference:** `pest_water_ini(ipesti)%benthic` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L334)).

Array of `cs_db%num_pests` initial pesticide values for benthic sediment, read in [`pest_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_cha_res_read.f90#L64).

For **SWAT-DEG channels** ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L265-L266)), `benthic` is multiplied by active benthic bed volume $V_{\text{bed}}$ (`m^3`) and `1000.` to initialize `ch_benthic(ich)%pest(ipest)` (`mg`):

$$M_{\text{ben}} = C_{\text{ben}} \cdot V_{\text{bed}} \cdot 1000, \qquad V_{\text{bed}} = W_{\text{ch}} \cdot L_{\text{ch}} \cdot 1000 \cdot d_{\text{act}}$$

where:
* $M_{\text{ben}}$ is initial benthic pesticide mass (`mg`),
* $C_{\text{ben}}$ is `benthic`,
* $V_{\text{bed}}$ is active benthic bed volume (`m^3`),
* $W_{\text{ch}}$ is channel width (`sd_ch(ich)%chw`, `m`),
* $L_{\text{ch}}$ is channel length (`sd_ch(ich)%chl`, `km`), and
* $d_{\text{act}}$ is `pestdb(ipest_ini)%ben_act_dep` (`m`; note the source indexes `pestdb` by initialization-set index `ipest_ini` rather than `ipest`).

For **reservoirs** ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L111)), `benthic` is copied directly into `res_benthic(ires)%pest(ipest)` without bed-volume scaling.
