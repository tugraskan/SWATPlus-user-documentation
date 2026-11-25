---
description: Time of concentration
---

# t\_conc

**Code reference:** `hlt_db(i)%tc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L15)).

Time of concentration in minutes. SWAT+ converts it to seconds ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L272)) and uses it for the surface runoff peak rate ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L354)), which affects sediment yield:

$$q_{peak} = \frac{2 \, Q}{1.5 \, t_c}$$

where $q_{peak}$ is the surface runoff peak rate (`m^3/s`), $Q$ is the runoff volume (`m^3`), and $t_c$ is `t_conc` converted to seconds. Enter a positive value. The fallback for a value of 0 divides by a slope variable that is never set ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L247-L253)), so it does not give a usable time.
