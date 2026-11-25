---
description: Light extinction coefficient
---

# ext\_co

**Code reference:** `pldb(ic)%ext_coef` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L79)).

**Current use:** values below `1e-6` are replaced by 0.65 ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L21)). Intercepted photosynthetically active radiation is calculated in [`pl_community.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_community.f90#L134) as:

$$\text{PAR}_{\text{int}} = 0.5\,H_{\text{day}}\left(1 - \exp\!\big(-k_{l}\,(\text{LAI} + 0.05)\big)\right)$$

where $\text{PAR}_{\text{int}}$ is intercepted photosynthetically active radiation (`MJ/m^2/day`), $H_{\text{day}}$ is daily solar radiation (`MJ/m^2/day`), $k_{l}$ is `ext_co` (dimensionless), and $\text{LAI}$ is leaf area index (dimensionless).

This coefficient is used to calculate the amount of intercepted photosynthetically active radiation.

Differences in canopy structure for a species are described by the number of leaves present (leaf area index) and the leaf orientation. Leaf orientation has a significant impact on light interception and consequently on radiation-use efficiency. More erect leaf types spread the incoming light over a greater leaf area, decreasing the average light intensity intercepted by individual leaves (see figure below). A reduction in light intensity interception by an individual leaf favors a more complete conversion of total canopy-intercepted light energy into biomass.

![](<../../../.gitbook/assets/image (18).png>)

Using the light extinction coefficient value ($k_l$) in the Beer-Lambert formula to quantify efficiency of light interception per unit leaf area index, more erect leaf types have a smaller $k_l$.

To calculate the light extinction coefficient, the amount of photosynthetically active radiation (PAR) intercepted and the leaf area index (LAI) are measured several times throughout a plant’s growing season using the methodology described in the previous sections. The light extinction coefficient is then calculated using the Beer-Lambert equation:

$$\frac{\text{TPAR}}{\text{PAR}} = 1 - \exp(-k_{l} \cdot \text{LAI}), \qquad k_{l} = -\ln\!\left(\frac{\text{TPAR}}{\text{PAR}}\right) \cdot \frac{1}{\text{LAI}}$$

where $\text{TPAR}$ is the transmitted photosynthetically active radiation (`MJ/m^2/day`), $\text{PAR}$ is the incoming photosynthetically active radiation (`MJ/m^2/day`), $k_l$ is `ext_co` (dimensionless), and $\text{LAI}$ is the leaf area index (dimensionless).
