---
description: "Heat-unit accumulation fraction"
---

# phuacc

**Code reference:** `transpl(ic)%phuacc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L149), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_transplant_read.f90#L43)).

Dimensionless fraction of annual potential heat units already accumulated at transplanting (struct default `0.0`). In [`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L24-L44), it initializes `pcom(j)%plcur(ipl)%phuacc`, enters the perennial lifetime heat-unit fraction `phuacc_p`, and drives initial leaf-area fraction (`laimxfr`, `laimxfr_p`) and plant N and P fractions:

$$f_{\text{phu},p} = f_{\text{mat}} + \frac{\text{PHU}_{\text{mat}} \cdot f_{\text{phu}}}{\text{PHU}_{\text{mat},p}}$$

where $f_{\text{phu}}$ is `phuacc`, $f_{\text{mat}}$ is [fr\_yrmat](fr_yrmat.md), $\text{PHU}_{\text{mat}}$ is annual heat units to maturity (`phumat`), and $\text{PHU}_{\text{mat},p}$ is perennial lifetime heat units to maturity (`phumat_p`).
