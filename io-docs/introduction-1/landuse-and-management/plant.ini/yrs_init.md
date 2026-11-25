---
description: Fraction of years to maturity completed (despite legacy yrs_init label)
---

# yrs\_init

**Code reference:** `pcomdb(icom)%pl(iplt)%fr_yrmat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L133), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L70)).

Despite the legacy label `yrs_init` and `years` unit in older documentation, SWAT+ main (`6f515368`) reads this column into `fr_yrmat` (struct default `1.0`) as a dimensionless **fraction of years to maturity** ($f_{\text{mat}}$, typically `0.0–1.0`), not an age in years:

**Initial canopy height and maturity fraction:** For perennials, sets initial canopy height ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L290-L292)) and maturity fraction for leaf/nutrient initialization ([`#L302-L328`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_init.f90#L302-L328)):

$$h_c = f_{\text{mat}} \cdot h_{c,\max}$$

where $h_c$ is initial perennial canopy height (`m`), $f_{\text{mat}}$ is `yrs_init` (dimensionless), and $h_{c,\max}$ is maximum canopy height (`m`).

**Integer growth year:** Sets the integer growth year ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L309-L310)):

$$\text{curyr}_{\text{mat}} = \max\!\big(1,\; \lfloor f_{\text{mat}} \cdot \text{mat}_{\text{yrs}} \rfloor\big)$$

where $\text{curyr}_{\text{mat}}$ is the integer plant growth year (`years`), $f_{\text{mat}}$ is `yrs_init` (dimensionless), and $\text{mat}_{\text{yrs}}$ is the species' years to maturity (`mat_yrs`, `years`).

**Perennial lifetime heat-unit fraction:** Initializes `phuacc_p` when [lc\_status](lc_status.md) is `"y"` ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L341-L347)).
