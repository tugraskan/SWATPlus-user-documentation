---
description: Normal fraction of phosphorus in plant at 50% maturity
---

# frac\_p\_50

**Code reference:** `pldb(ic)%pltpfr2`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L66)).

In order to calculate the plant nutrient demand throughout a plant’s growing cycle, SWAT+ needs to know the fraction of nutrient in the total plant biomass (on a dry weight basis) at different stages of crop growth. Six variables in the plant database provide this information: [frac\_n\_em](frac_p_em.md), [frac\_n\_50](frac_n_50.md), [frac\_n\_mat](frac_n_mat.md), [frac\_p\_em](frac_p_em.md), _frac\_p\_50_, and [frac\_p\_mat](frac_p_mat.md). Plant samples are analyzed for nitrogen and phosphorus content at three times during the growing season: shortly after emergence, near the middle of the season, and at maturity. Ideally, the plant samples tested for nutrient content should include the roots as well as the aboveground biomass. Differences in partitioning of nutrients to roots and shoots can cause erroneous conclusions when comparing productivity among species if only the aboveground biomass is measured.
