---
description: Curve number for hydrologic soil group C
---

# cn\_c

**Code reference:** `cn(icno)%cn(3)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L40), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cntbl_read.f90#L45)).

Dimensionless SCS moisture-condition II runoff curve number (`30.0–100.0`, struct default `70.0`) assigned to HRUs with Hydrologic Soil Group C in [`cn2_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cn2_init.f90#L28). In [`curno.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/curno.f90#L58-L69), SWAT+ converts $\text{CN}_{2}$ to dry (condition I) and wet (condition III) curve numbers and the maximum retention parameter $S_{\max}$ (`mm`):

$$\text{CN}_1 = \max\!\left(\text{CN}_2 - \frac{20\,(100 - \text{CN}_2)}{(100 - \text{CN}_2) + \exp\big(2.533 - 0.0636\,(100 - \text{CN}_2)\big)},\; 0.4\,\text{CN}_2\right)$$

where $\text{CN}_{1}$ is the moisture-condition I (dry) curve number (dimensionless) and $\text{CN}_{2}$ is `cn_c` (dimensionless).

$$S_{\max} = 254\left(\frac{100}{\text{CN}_1} - 1\right), \quad \text{CN}_3 = \text{CN}_2 \exp\!\big(0.006729\,(100 - \text{CN}_2)\big)$$

where $S_{\max}$ is the maximum retention parameter (`mm`), $\text{CN}_{1}$ is the moisture-condition I curve number (dimensionless), $\text{CN}_{2}$ is `cn_c` (dimensionless), and $\text{CN}_{3}$ is the moisture-condition III (wet) curve number (dimensionless).
