---
description: "Amount of constituent in soil at start of simulation"
---

# soil

**Code reference:** `cs_soil_ini(ics)%soil` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L291)).

Array of `2 * cs_db%num_cs` real values allocated and read in [`cs_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_read.f90#L51-L70), applied uniformly across every soil layer in [`cs_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_init.f90#L48-L68):

**First `cs_db%num_cs` entries** (dissolved concentrations, `g/m^3` = `mg/L`): stored in `cs_soil(ihru)%ly(ly)%csc(ics)` ([`cs_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_init.f90#L57)) and converted to dissolved constituent mass (`kg/ha`) ([`cs_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_init.f90#L59-L60)):

$$M_{\text{cs},l,k} = \frac{C_{k}}{1000} \cdot \frac{V_{w,l}}{A_{\text{hru}}}, \qquad V_{w,l} = \frac{\text{SW}_{l}}{1000} \cdot (10000 \cdot A_{\text{hru}})$$

where:
* $M_{\text{cs},l,k}$ is dissolved mass of constituent $k$ in soil layer $l$ (`kg/ha`),
* $C_{k}$ is the dissolved input concentration in `soil` (`g/m^3`),
* $V_{w,l}$ is layer soil water volume (`m^3`),
* $\text{SW}_{l}$ is layer soil water (`soil%phys(ly)%st`, `mm`), and
* $A_{\text{hru}}$ is HRU area (`ha`).

**Next `cs_db%num_cs` entries** (sorbed concentrations on soil solids, `mg/kg` = `ppm`): stored in `cs_soil(ihru)%ly(ly)%csc_sorb(ics)` ([`cs_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_init.f90#L62)) and converted to sorbed mass (`kg/ha`) ([`cs_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_init.f90#L64-L67)):

$$M_{\text{sorb},l,k} = \frac{C_{\text{sorb},k} \cdot M_{\text{soil},l}}{10^{6} \cdot A_{\text{hru}}}, \qquad M_{\text{soil},l} = (10000 \cdot A_{\text{hru}}) \cdot \frac{\Delta z_{l}}{1000} \cdot (1000 \cdot \rho_{b,l})$$

where:
* $M_{\text{sorb},l,k}$ is sorbed mass of constituent $k$ in soil layer $l$ (`kg/ha`),
* $C_{\text{sorb},k}$ is the sorbed input concentration in `soil` (`mg/kg`),
* $M_{\text{soil},l}$ is soil layer solid mass (`kg`),
* $A_{\text{hru}}$ is HRU area (`ha`),
* $\Delta z_{l}$ is layer thickness (`soil%phys(ly)%thick`, `mm`), and
* $\rho_{b,l}$ is layer bulk density (`soil%phys(ly)%bd`, `t/m^3`).
