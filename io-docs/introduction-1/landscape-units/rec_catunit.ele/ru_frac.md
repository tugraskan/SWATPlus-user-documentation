---
description: "Routing-unit expansion fraction"
---

# ru\_frac

**Code reference:** `pcu_elem(i)%ru_frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L225), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L162)).

Routing-unit expansion fraction for the point-source element (`real`, `fraction`, default `0.0`). In [`rec_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L176), it is multiplied by `pcu_cal(ireg)%area_ha` (which remains `0.0`), and `pcu_cal%hru_ha` is never read afterward:

$$A_{\text{cal}} = f_{\text{ru}} \cdot A_{\text{reg}}$$

where $A_{\text{cal}}$ is `pcu_cal%hru_ha` (`ha`), $f_{\text{ru}}$ is `ru_frac` (`fraction`), and $A_{\text{reg}}$ is `pcu_cal(ireg)%area_ha` (`ha`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
