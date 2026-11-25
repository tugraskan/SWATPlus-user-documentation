---
description: Area of the Landscape Unit in hectares
---

# area

**Code reference:** `lsu_out(i)%area_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L195), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L70)).

Area of the Landscape Unit in hectares (`real`, `ha`, struct default `0.0`).

In SWAT+ main (`6f515368`), `lsu_out%area_ha` is only referenced in the uncalled routine [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L196) to compute HRU areas in a calibration region:

$$A_{\text{reg,hru}} = f_{\text{ru}} \cdot A_{\text{lsu}}$$

where $A_{\text{reg,hru}}$ is the HRU area in the calibration region (`ha`), $f_{\text{ru}}$ is the element routing-unit fraction (`fraction`), and $A_{\text{lsu}}$ is `area` (`ha`). Active LSU output aggregation instead weights HRUs directly by [`ru_frac`](../ls_unit.ele/ru_frac.md) from [`ls_unit.ele`](../ls_unit.ele/README.md).
