---
description: "Plant population"
---

# pop

**Code reference:** `transpl(ic)%pop` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L151), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_transplant_read.f90#L43)).

Plant population (`plants/m^2`, struct default `0.0`). Although the source declaration comment says `not currently used`, SWAT+ main (`6f515368`) actively uses `transpl(itrans)%pop` in [`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L47-L53) to set potential maximum LAI (`lai_pot`):

$$\text{LAI}_{\text{pot}} = \begin{cases} \text{BLAI}, & \text{pop} < 10^{-6} \\ \dfrac{\text{BLAI} \cdot \text{pop}}{\text{pop} + \exp(\text{popsc}_1 - \text{popsc}_2 \cdot \text{pop})}, & \text{pop} \ge 10^{-6} \end{cases}$$

where $\text{BLAI}$ is the plant database maximum LAI (`pldb%blai`) and $\text{popsc}_{1}, \text{popsc}_{2}$ are the plant population curve shape parameters (`plcp`).
