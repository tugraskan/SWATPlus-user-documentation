---
description: "Salt ion concentration at the start of the simulation"
---

# conc

**Code reference:** `salt_aqu_ini(isalt)%conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L304)).

Array of `cs_db%num_salts` (typically 8: `SO4`, `Ca`, `Mg`, `Na`, `K`, `Cl`, `CO3`, `HCO3`) initial groundwater salt ion concentrations (`g/m^3`, equivalent to `mg/L`), allocated and read in [`salt_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aqu_read.f90#L48-L63). In [`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L117-L120), SWAT+ stores the concentration in `cs_aqu(iaq)%saltc(isalt)` and converts it to dissolved salt mass (`kg`) using initial groundwater volume ([`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L74)):

$$M_{\text{aqu},k} = \frac{C_{k} \cdot V_{\text{gw}}}{1000}, \qquad V_{\text{gw}} = \frac{S_{\text{aqu}}}{1000} \cdot (10000 \cdot A_{\text{aqu}})$$

where $S_{\text{aqu}}$ is initial aquifer water storage (`aqu_d(iaq)%stor`, `mm`) and $A_{\text{aqu}}$ is aquifer object area (`ob(iob)%area_ha`, `ha`).
