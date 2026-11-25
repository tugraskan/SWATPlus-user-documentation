---
description: Initial pesticide values for water
---

# water

**Code reference:** `pest_water_ini(ipesti)%water` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L333)).

Array of `cs_db%num_pests` initial pesticide values for water, read in [`pest_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_cha_res_read.f90#L64). SWAT+ applies these values differently by spatial object:

For **SWAT-DEG channels** ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L263)), `water` is treated as concentration (`mg/L` = `ppm`) and converted to channel-water pesticide mass (`mg`) using channel water volume $V_{\text{ch}}$ (`ch_stor(ich)%flo`, `m^3`):

$$M_{\text{ch}} = C_{\text{water}} \cdot V_{\text{ch}} \cdot 1000$$

where $M_{\text{ch}}$ is initial channel-water pesticide mass (`mg`), $C_{\text{water}}$ is `water` (`mg/L`), and $V_{\text{ch}}$ is channel water volume (`ch_stor(ich)%flo`, `m^3`).

For **aquifers** ([`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L89)), `water` is scaled by aquifer bottom depth $d_{\text{bot}}$ (`aqudb(iaq)%dep_bot`, `m`):

$$M_{\text{aqu}} = C_{\text{water}} \cdot 2.0 \cdot d_{\text{bot}} \cdot 10$$

where $M_{\text{aqu}}$ is initial aquifer pesticide mass, $C_{\text{water}}$ is `water`, and $d_{\text{bot}}$ is `aqudb(iaq)%dep_bot` (`m`).

For **reservoirs** ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L110)), `water` is copied directly into `res_water(ires)%pest(ipest)` without volume scaling.
