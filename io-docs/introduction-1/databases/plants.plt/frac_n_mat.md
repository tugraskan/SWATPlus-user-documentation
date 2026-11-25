---
description: Normal fraction of nitrogen in plant biomass at maturity
---

# frac\_n\_mat

**Code reference:** `pldb(ic)%pltnfr3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L59)).

**Current use:** the three N fractions are fitted to a curve over maturity (heat-unit fraction for annuals, years for perennials) that sets the daily N demand ([`pl_nupd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nupd.f90#L46-L54)). If the mid-season value is not at least 0.0001 above it, it is multiplied by 0.75. ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L66-L74)).

In order to calculate the plant nutrient demand throughout a plant’s growing cycle, SWAT+ needs to know the fraction of nutrient in the total plant biomass (on a dry weight basis) at different stages of crop growth. Six variables in the plant database provide this information: [frac\_n\_em](frac_n_em.md), [frac\_n\_50](frac_n_50.md), _frac\_n\_mat_, [frac\_p\_em](frac_p_em.md), [frac\_p\_50](frac_p_50.md), and [frac\_p\_mat](frac_p_mat.md). Plant samples are analyzed for nitrogen and phosphorus content at three times during the growing season: shortly after emergence, near the middle of the season, and at maturity. Ideally, the plant samples tested for nutrient content should include the roots as well as the aboveground biomass. Differences in partitioning of nutrients to roots and shoots can cause erroneous conclusions when comparing productivity among species if only the aboveground biomass is measured.
