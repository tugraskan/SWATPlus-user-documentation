---
description: Soil adsorption coefficient normalized for soil organic carbon content
---

# soil\_ads

**Code reference:** `pestdb(ip)%koc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L7)).

**Current use:** SWAT+ multiplies this value by the organic carbon fraction to partition pesticide in soil leaching ([`pest_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_lch.f90#L44-L46)), plant uptake ([`pest_pl_up.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L66-L67)), channels ([`ch_rtpest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L97-L113)) and reservoirs ([`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L57-L66)). Suspected defect: the sediment-loss routine uses the surface layer's carbon **mass** instead of its percentage ([`pest_pesty.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pesty.f90#L35)).

Pesticides in the soil environment can be transported in solution or attached to sediment. The partitioning of a pesticide between the solution and soil phases is defined by the soil adsorption coefficient for the pesticide. The soil adsorption coefficient is the ratio of the pesticide concentration in the soil or solid phase to the pesticide concentration in the solution or liquid phase:

$$K_p = \frac{C_{\text{solidphase}}}{C_{\text{solution}}}$$

where $K_p$ is the soil adsorption coefficient (`(mg/kg)/(mg/L)` or `m3/ton`), $C_{\text{solidphase}}$ is the concentration of the pesticide sorbed to the solid phase (`mg chemical/kg solid material` or `g/ton`), and $C_{\text{solution}}$ is the concentration of the pesticide in solution (`mg chemical/L solution` or `g/ton`). The definition of the soil adsorption coefficient in this equation assumes that the pesticide sorption process is linear with concentration and instantaneously reversible. Because the partitioning of pesticide is dependent upon the amount of organic material in the soil, the soil adsorption coefficient input to the model is normalized for soil organic carbon content. The relationship between the soil adsorption coefficient and the soil adsorption coefficient normalized for soil organic carbon content is:

$$K_p = K_{\text{oc}} \cdot \frac{\text{orgC}}{100}$$

where $K_p$ is the soil adsorption coefficient (`(mg/kg)/(mg/L)`), $K_{\text{oc}}$ is the soil adsorption coefficient normalized for soil organic carbon content (`(mg/kg)/(mg/L)` or `m3/ton`), and $\text{orgC}$ is the percent organic carbon present in the soil (`%`).
