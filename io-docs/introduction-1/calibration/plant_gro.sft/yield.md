---
description: Average annual crop yield soft-calibration target in plant_gro.sft.
---

# yield

**Code reference:** `plcal(i)%lum(ilum)%meas%yield` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L244), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L49-L516)).

Average annual dry-weight crop yield target (`t/ha`, struct default `0.`). Compared against the area-weighted simulated annual yield computed by [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L580) and [`calsoft_ave_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_ave_output.f90#L68):

$$\bar{Y} = \frac{1}{A_{\text{tot}}} \sum_j \frac{Y_j A_j}{1000}$$

where $\bar{Y}$ is the area-weighted simulated annual crop yield (`t/ha`), $A_{\text{tot}}$ is total land-use area (`ha`), $Y_j$ is simulated crop yield for HRU $j$ (`kg/ha`), and $A_j$ is the area of HRU $j$ (`ha`).

When the relative error $|Y_{\text{soft}} - \bar{Y}| / Y_{\text{soft}} > 0.03$, [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L49-L516) sequentially adjusts `epco`, `pest_stress`, `lai_pot`, and `harv_idx` within the bounds from `plant_parms.sft`.
