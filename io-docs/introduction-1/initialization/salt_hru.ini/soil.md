---
description: Initial salt ion concentrations and mineral percentages in HRU soil
---

# soil

**Code reference:** `salt_soil_ini(isalti)%soil` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L291)).

Array of `cs_db%num_salts + 5` values allocated and read in [`salt_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_read.f90#L50-L69), applied uniformly across every soil layer in [`salt_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L51-L68):

**First `cs_db%num_salts` entries** (dissolved salt ions `SO4`, `Ca`, `Mg`, `Na`, `K`, `Cl`, `CO3`, `HCO3` in `mg/L` = `g/m^3`): stored in `cs_soil(ihru)%ly(ly)%saltc(isalt)` ([`salt_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L55)) and converted to soil-layer salt mass (`kg/ha`) using each layer's initial water volume ([`salt_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L57-L58)):

$$M_{\text{salt},l,k} = \frac{C_{k}}{1000} \cdot \frac{V_{w,l}}{A_{\text{hru}}}, \qquad V_{w,l} = \frac{\text{SW}_{l}}{1000} \cdot (10000 \cdot A_{\text{hru}})$$

where:
* $M_{\text{salt},l,k}$ is dissolved mass of salt ion $k$ in soil layer $l$ (`kg/ha`),
* $C_{k}$ is the dissolved input concentration in `soil` (`mg/L`),
* $V_{w,l}$ is layer initial water volume (`m^3`),
* $\text{SW}_{l}$ is layer soil water (`soil%phys(ly)%st`, `mm`), and
* $A_{\text{hru}}$ is HRU area (`ha`).

**Next 5 entries** (salt minerals `CaCO3`, `MgCO3`, `CaSO4`, `MgSO4`, `NaCl`): copied into `cs_soil(ihru)%ly(ly)%salt_min(1:5)` ([`salt_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L64-L67)). Although source comments refer to "salt mineral fractions" ([`constituent_mass_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L298)), [`salt_chem_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L113-L120) (and [`salt_chem_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L350)) and [`salt_balance.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L325) divide `salt_min` by `100.` and cap it at `100.`, treating these inputs as **percent (`%`, `0–100`)** of soil solid mass.
