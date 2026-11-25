---
description: Normal fraction of phosphorus in plant at 50% maturity
---

# frac\_p\_50

**Code reference:** `pldb(ic)%pltpfr2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L61)).

**Current use:** the three P fractions are fitted to a curve over maturity (heat-unit fraction for annuals, years for perennials) that sets the daily P demand ([`pl_pupd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_pupd.f90#L50-L59)). The model lowers it if needed to stay 0.0001 below the emergence value. ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L78-L86)).

In order to calculate the plant nutrient demand throughout a plant’s growing cycle, SWAT+ needs to know the fraction of nutrient in the total plant biomass (on a dry weight basis) at different stages of crop growth. Six variables in the plant database provide this information: [frac\_n\_em](frac_n_em.md), [frac\_n\_50](frac_n_50.md), [frac\_n\_mat](frac_n_mat.md), [frac\_p\_em](frac_p_em.md), _frac\_p\_50_, and [frac\_p\_mat](frac_p_mat.md). Plant samples are analyzed for nitrogen and phosphorus content at three times during the growing season: shortly after emergence, near the middle of the season, and at maturity. Ideally, the plant samples tested for nutrient content should include the roots as well as the aboveground biomass. Differences in partitioning of nutrients to roots and shoots can cause erroneous conclusions when comparing productivity among species if only the aboveground biomass is measured.
