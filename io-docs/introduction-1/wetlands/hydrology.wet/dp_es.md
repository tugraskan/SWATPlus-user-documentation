---
description: Average depth of water at emergency spillway
---

# dp\_es

**Code reference:** `wet_hyddb(ires)%edep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L87)).

The average depth of water at the emergency spillway (in millimeters) is used to calculate the emergency spillway storage volume capacity of the wetland (`wet_ob%evol` in $\text{m}^3$). 

During initialization ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L133), [`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L111)), SWAT+ calculates the emergency volume from the HRU area:

$$V_{\text{evol}} = \text{area} \times \text{depth} \times 10$$

where $V_{\text{evol}}$ is emergency storage capacity in $\text{m}^3$ (`wet_ob%evol`), $\text{area}$ is HRU area in hectares (`hru%area_ha`), and $\text{depth}$ is the emergency spillway depth in millimeters (`dp_es`).

*(Note: In SWAT+ main (6f515368), the model assumes for simplicity that the entire HRU is impounded, so [`hru_es`](hru_es.md) is not multiplied into this volume calculation).*

The calculated emergency volume defines the threshold above which impounded water spills over the emergency spillway into the downstream network. Under normal wetland configurations, `dp_es` should be greater than [`dp_ps`](dp_ps.md).
