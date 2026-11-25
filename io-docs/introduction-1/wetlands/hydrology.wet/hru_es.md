---
description: Fraction of HRU area at emergency spillway
---

# hru\_es

**Code reference:** `wet_hyddb(ires)%esa` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L86)).

During initialization ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L136)), `hru_es` is multiplied by the HRU area to calculate emergency surface area (`wet_ob%esa`, ha):

$$A_{\text{esa}} = f_{\text{es}} \cdot A_{\text{hru}}$$

where $A_{\text{esa}}$ is emergency surface area (ha), $f_{\text{es}}$ is `hru_es`, and $A_{\text{hru}}$ is HRU area (ha). If `hru_es <= 0.0`, [`wet_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L61) sets it to $1.5 \cdot f_{\text{ps}}$ (`1.5 * wet_hyd(ires)%psa`).

In SWAT+ main (6f515368), the resulting `wet_ob%esa` value is not used by subsequent active wetland calculations. The input fraction can also appear in [SWIFT output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swift_output.f90#L182).
