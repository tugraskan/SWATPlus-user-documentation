---
description: >-
  Maximum stomatal conductance at high solar radiation and low vapor pressure
  deficit
---

# stcon\_max

**Code reference:** `pldb(ic)%gsi`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L70)).

Stomatal conductance of water vapor is used in the Penman-Monteith calculations of maximum plant evapotranspiration. The plant database contains three variables pertaining to stomatal conductance that are required only if the Penman-Monteith equation is used to model evapotranspiration: maximum stomatal conductance and two variables that define the impact of vapor pressure deficit on stomatal conductance ([frac\_stcon](frac_stcon.md), [vpd](vpd.md)).

Körner et al. (1979) defines maximum leaf diffusive conductance as the largest value of conductance observed in fully developed leaves of well-watered plants under optimal climatic conditions, natural outdoor CO2 concentrations and sufficient nutrient supply. Leaf diffusive conductance of water vapor cannot be measured directly but can be calculated from measurements of transpiration under known climatic conditions. Various different methods are used to determine diffusive conductance: transpiration measurements in photosynthesis cuvettes, energy balance measurements or weighing experiments, ventilated diffusion porometers, and non-ventilated porometers. Körner (1977) measured diffusive conductance using a ventilated diffusion porometer.

To obtain maximum leaf conductance values, leaf conductance is determined between sunrise and late morning until a clear decline or no further increase is observed. Depending on phenology, measurements are taken on at least three bright days in late spring and summer, preferably just after a rainy period. The means of maximum leaf conductance of 5 to 10 samples each day are averaged, yielding the maximum diffusive conductance for the species. Due to the variation of the location of stomata on plant leaves for different plant species, conductance values should be calculated for the total leaf surface area.

#### References

> Körner (1977)&#x20;
>
> Körner et al. (1979)
