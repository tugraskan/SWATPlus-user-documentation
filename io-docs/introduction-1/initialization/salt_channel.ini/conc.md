---
description: "Initial salt ion concentration at the start of the simulation"
---

# conc

**Code reference:** `salt_cha_ini(isalti)%conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L319)).

Array of `cs_db%num_salts` initial channel-water salt ion concentrations (`g/m^3`, equivalent to `mg/L`), allocated and read in [`salt_cha_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_cha_read.f90#L44-L54). In [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L291-L294), SWAT+ stores the concentration in `ch_water(ich)%saltc(isalt)` and converts it to dissolved salt mass (`kg`) using initial total channel water volume $V_{\text{tot}}$ (`tot_stor(ich)%flo`, `m^3`):

$$M_{\text{ch},k} = \frac{C_{k}}{1000} \cdot V_{\text{tot}}$$

where $M_{\text{ch},k}$ is dissolved channel salt mass of ion $k$ (`kg`), $C_{k}$ is the input concentration in `conc` (`g/m^3`), and $V_{\text{tot}}$ is initial total channel water volume (`tot_stor(ich)%flo`, `m^3`).
