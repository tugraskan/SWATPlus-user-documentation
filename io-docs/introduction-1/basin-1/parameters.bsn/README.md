---
description: This file contains basin-level parameters.
---

# parameters.bsn

Basin-wide physical and calibration parameters, read sequentially into `bsn_prm` by [`basin_read_prm.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L15-L28) with runtime defaults and overrides applied in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L9-L61).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [lai\_noevap](lai_noevap.md) | Currently not used | real |  |  |  |
| [sw\_init](sw_init.md) | Initial soil water storage expressed as a fraction of field capacity water content | real |  | 0 | 0-1 |
| [surq\_lag](surq_lag.md) | Surface runoff lag time | real | days | 4 | 1-24 |
| [adj\_pkrt](adj_pkrt.md) | Adjustment factor for the weather-generator half-hour rainfall fraction | real |  | 1 | 0.5-2 |
| [adj\_pkrt\_sed](adj_pkrt_sed.md) | Peak rate factor for the NRCS dimensionless-hydrograph peak-runoff equation | real |  | 1 | 0-2 |
| [lin\_sed](lin_sed.md) | Pesticide groundwater mixing-volume factor | real | fraction | 0 | 0-1 |
| [exp\_sed](exp_sed.md) | Temperature-dependent pesticide decay switch (1 = on; other values = off) | real | n/a | 0 | 0-1 |
| [orgn\_min](orgn_min.md) | Rate factor for humus mineralization of active organic nutrients (N and P) | real |  | 0.0003 | 0.0003-0.003 |
| [n\_uptake](n_uptake.md) | Nitrogen uptake distribution parameter | real |  | 20 | 0-100 |
| [p\_uptake](p_uptake.md) | Phosphorus uptake distribution parameter | real |  | 20 | 0-100 |
| [n\_perc](n_perc.md) | Nitrate percolation coefficient | real |  | 0.1 | 0-1 |
| [p\_perc](p_perc.md) | Phosphorus percolation coefficient | real | 10 m^3/Mg | 10 | 10-17.5 |
| [p\_soil](p_soil.md) | Phosphorus soil partitioning coefficient | real | m^3/Mg | 175 | 100-200 |
| [p\_avail](p_avail.md) | Phosphorus availability index | real |  | 0.4 | 0.01-0.7 |
| [rsd\_decomp](rsd_decomp.md) | Residue decomposition coefficient | real |  | 0.05 | 0.02-0.1 |
| [pest\_perc](pest_perc.md) | Pesticide percolation coefficient | real |  | 0.5 | 0-1 |
| [msk\_co1](msk_co1.md) | Coefficient to control the impact of the storage time constant for normal flow on the overall storage time constant for the channel | real |  | 0.75 | 0-10 |
| [msk\_co2](msk_co2.md) | Coefficient to control the impact of the storage time constant for low flow on the overall storage time constant for the channel | real |  | 0.25 | 0-10 |
| [msk\_x](msk_x.md) | Weighting factor control relative importance of inflow rate and outflow rate in determining storage on reach | real |  | 0.2 | 0-0.3 |
| [nperco\_lchtile](nperco_lchtile.md) | Nitrogen concentration coefficient for tile flow (not applied to bottom-layer percolation leaching in main 6f515368) | real |  | 0.5 | 0-1 |
| [evap\_adj](evap_adj.md) | Reach evaporation adjustment factor | real |  | 0.6 | 0.5-1 |
| [scoef](scoef.md) | Multiplier for the variable-storage channel-routing coefficient | real | n/a | 1 | 0-1 |
| [denit\_exp](denit_exp.md) | Denitrification exponential rate coefficient | real |  | 1.4 | 0-3 |
| [denit\_frac](denit_frac.md) | Denitrification threshold as a fraction of field capacity | real | fraction | 1.3 |  |
| [man\_bact](man_bact.md) | Currently not used | real |  |  |  |
| [adj\_uhyd](adj_uhyd.md) | Adjustment factor for subdaily unit hydrograph basetime | real |  | 0 | 0-1 |
| [cn\_froz](cn_froz.md) | Parameter for frozen soil adjustment on infiltration/runoff | real |  | 0.000862 |  |
| [dorm\_hr](dorm_hr.md) | Time threshold used to define dormancy | real | hrs | 0 | 0-24 |
| [plaps](plaps.md) | Precipitation lapse rate | real | mm/km |  |  |
| [tlaps](tlaps.md) | Temperature lapse rate | real | deg C/km |  |  |
| [n\_fix\_max](n_fix_max.md) | Maximum daily nitrogen fixation | real | kg/ha | 20 | 1-20 |
| [rsd\_decay](rsd_decay.md) | Minimum daily residue decay | real | fraction | 0.01 | 0-0.05 |
| [rsd\_cover](rsd_cover.md) | Residue-cover coefficient used in the C-factor calculation | real |  | 0.75 |  |
| [urb\_init\_abst](urb_init_abst.md) | Maximum initial abstraction for urban areas | real |  | 5 | 0-10 |
| [petco\_pmpt](petco_pmpt.md) | Currently not used | real |  |  |  |
| [uhyd\_alpha](uhyd_alpha.md) | Alpha coefficient for gamma function unit hydrograph | real |  | 5 | 0.5-10 |
| [splash](splash.md) | Splash erosion coefficient | real |  | 1 | 0.9-3.1 |
| [rill](rill.md) | Rill erosion coefficient | real |  | 0.7 | 0.5-2 |
| [surq\_exp](surq_exp.md) | Exponential coefficient for overland flow | real |  | 1.2 | 1-3 |
| [cov\_mgt](cov_mgt.md) | Scaling parameter for cover and management factor for overland flow erosion | real |  | 0.03 | 0.001-0.45 |
| [cha\_d50](cha_d50.md) | Currently not used | real |  |  |  |
| [co2](co2.md) | CO2 concentration at start of simulation | real | ppm | 400 | &gt;=100 |
| [day\_lag\_max](day_lag_max.md) | Input value is ignored; SWAT+ sets the internal maximum hydrograph lag to 2 days | integer | days |  |  |
| [igen](igen.md) | Random-number seed code (0 = fixed default seeds; nonzero = advance and replace the seeds) | integer | n/a |  |  |
