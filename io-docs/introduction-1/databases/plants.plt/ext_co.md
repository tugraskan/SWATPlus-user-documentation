---
description: Light extinction coefficient
---

# ext\_co

**Code reference:** `pldb(ic)%ext_coef`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L84)).

This coefficient is used to calculate the amount of intercepted photosynthetically active radiation.

Differences in canopy structure for a species are described by the number of leaves present (leaf area index) and the leaf orientation. Leaf orientation has a significant impact on light interception and consequently on radiation-use efficiency. More erect leaf types spread the incoming light over a greater leaf area, decreasing the average light intensity intercepted by individual leaves (see figure below). A reduction in light intensity interception by an individual leaf favors a more complete conversion of total canopy-intercepted light energy into biomass.

![](<../../../.gitbook/assets/image (18).png>)

Using the light extinction coefficient value (kℓ) in the Beer-Lambert formula to quantify efficiency of light interception per unit leaf area index, more erect leaf types have a smaller kℓ.

To calculate the light extinction coefficient, the amount of photosynthetically active radiation (PAR) intercepted and the mass of aboveground biomass (LAI) is measured several times throughout a plant’s growing season using the methodology described in the previous sections. The light extinction coefficient is then calculated using the Beer-Lambert equation:

$$\frac{TPAR}{PAR}=(1-exp⁡(-k_l⋅LAI))$$

or

$$k_l=-ln⁡(\frac{TPAR}{PAR}) * \frac{1}{LAI}$$

where _TPAR_ is the transmitted photosynthetically active radiation, and _PAR_ is the incoming photosynthetically active radiation.
