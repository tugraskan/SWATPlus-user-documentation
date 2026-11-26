---
description: "Routing-unit expansion fraction"
---

# ru\_frac

**Code reference:** `acu_elem(i)%ru_frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L225), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L174)).

Routing-unit expansion fraction for the aquifer element (`real`, `fraction`, default `0.0`). In [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L188), it is multiplied by `acu_cal(ireg)%area_ha` (which remains `0.0`), and `acu_cal%hru_ha` is never read afterward:

$$A_{\text{cal}} = f_{\text{ru}} \cdot A_{\text{reg}}$$

where $A_{\text{cal}}$ is `acu_cal%hru_ha` (`ha`), $f_{\text{ru}}$ is `ru_frac` (`fraction`), and $A_{\text{reg}}$ is `acu_cal(ireg)%area_ha` (`ha`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
