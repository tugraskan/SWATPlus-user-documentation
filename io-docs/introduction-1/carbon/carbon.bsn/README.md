---
description: "Basin-wide carbon cycling parameters and per-layer decomposition coefficients, read when codes.bsn carbon = 2."
---

{% hint style="info" %}
Field names in the tables follow the SWAT+ Fortran source. The reader takes values by position, so the column headings in the file are not checked; the SWAT+ example file uses other headings (given on each field page). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

# carbon.bsn

Basin-wide parameters for the dynamic soil carbon model. SWAT+ reads this file only when [carbon](../../basin-1/codes.bsn/carbon.md) in `codes.bsn` is `2` ([`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L47-L63)). The file is then required: the run stops if it is missing or if its data line does not hold all 28 values ([`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L67-L89)). It has a title line, a heading line and one data line.

{% hint style="warning" %}
The data line differs from SWAT+ main: the first value is now [frac\_litter](frac_litter.md), the complement of main's `frac_seq`; `n_act_frac` is no longer read; and [cbn\_diag\_int](cbn_diag_int.md) is added at the end. The count is still 28, so a main-format file is read without an error but with wrong values: the first value is inverted, and from `cnr_cap` on each value receives the number that main placed one column earlier (so `cnr_cap` gets the old `n_act_frac`, and `cbn_diag_int` gets the old `mathers_int`). Convert main files before running dev.
{% endhint %}

The per-layer coefficients belong in a companion file whose name is built from this one: `carbon.bsn` uses `carbon_lyr.bsn`, and a file listed in `file.cio` as `foo.bsn` uses `foo_lyr.bsn` ([`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L101-L109)). The companion is also required and is not listed in `file.cio`. It has a title line, a heading line and one row for each layer group.

## Basin parameters

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [frac_litter](frac_litter.md) | Fraction of initial soil organic carbon placed in the litter pools; the rest goes to the humus and microbial pools | real | fraction | — | — |
| [frac_hum_microb](frac_hum_microb.md) | Share of the non-litter carbon placed in the microbial pool | real | fraction | — | — |
| [frac_hum_slow](frac_hum_slow.md) | Share placed in the slow humus pool (when `mathers_int` is not 1) | real | fraction | — | — |
| [frac_hum_passive](frac_hum_passive.md) | Share placed in the passive humus pool | real | fraction | — | — |
| [prmt_21](prmt_21.md) | Partition coefficient (Koc) for microbial carbon loss from soil layer 1 with water | real | — | — | — |
| [prmt_44](prmt_44.md) | Ratio of soluble carbon concentration in runoff and lateral flow to that in percolate | real | ratio | — | — |
| [till_eff_days](till_eff_days.md) | Number of days a tillage operation affects carbon cycling | integer | days | — | — |
| [rtof](rtof.md) | Weighting factor splitting the organic N and P of applied fertilizer and manure between pools | real | fraction | — | — |
| [bio_consf](bio_consf.md) | Daily rate at which biological mixing recovers after tillage | real | fraction/day | — | — |
| [till_consf](till_consf.md) | Daily rate at which the tillage effect fades as soil settles | real | fraction/day | — | — |
| [tmpf](tmpf.md) | Soil temperature factor equation for decomposition (1, 2 or 3) | integer | n/a | — | — |
| [watf](watf.md) | Soil water factor equation for decomposition (1 or 2) | integer | n/a | — | — |
| [tn](tn.md) | Minimum temperature of the `tmpf = 2` temperature function | real | °C | — | — |
| [top](top.md) | Optimum temperature of the `tmpf = 2` temperature function | real | °C | — | — |
| [tx](tx.md) | Maximum temperature of the `tmpf = 2` temperature function | real | °C | — | — |
| [bmix_a](bmix_a.md) | Base value of the maximum biological mixing factor equation | real | — | — | — |
| [bmix_b](bmix_b.md) | Multiplier of the clay term in the maximum biological mixing factor equation | real | — | — | — |
| [bmix_c](bmix_c.md) | Clay exponent coefficient in the maximum biological mixing factor equation | real | — | — | — |
| [tillmix_a](tillmix_a.md) | Base value of the maximum tillage mixing factor equation | real | — | — | — |
| [tillmix_b](tillmix_b.md) | Multiplier of the clay term in the maximum tillage mixing factor equation | real | — | — | — |
| [tillmix_c](tillmix_c.md) | Clay exponent coefficient in the maximum tillage mixing factor equation | real | — | — | — |
| [photo_degrade_factor](photo_degrade_factor.md) | Daily fraction of surface residue lost to photodegradation | real | fraction/day | — | — |
| [cnr_cap](cnr_cap.md) | Upper limit on residue C:N ratio in the decomposition factor | real | ratio | — | — |
| [cnr_ref](cnr_ref.md) | Residue C:N ratio at which the nitrogen decomposition factor equals 1 | real | ratio | — | — |
| [cpr_cap](cpr_cap.md) | Upper limit on residue C:P ratio in the decomposition factor | real | ratio | — | — |
| [cpr_ref](cpr_ref.md) | Residue C:P ratio at which the phosphorus decomposition factor equals 1 | real | ratio | — | — |
| [mathers_int](mathers_int.md) | `1` sets the initial passive humus pool from clay and silt (Mathers method) | integer | n/a | — | — |
| [cbn_diag_int](cbn_diag_int.md) | `1` writes the detailed soil carbon diagnostic files | integer | n/a | — | — |

## carbon_lyr.bsn

Row `1` applies to soil layer 1, the 10 mm surface layer, and row `2` to all deeper layers.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [layer_id](layer_id.md) | Layer group of the row: 1 = soil layer 1, 2 = deeper layers | integer | n/a | — | — |
| [r_hp_rate](r_hp_rate.md) | Daily transformation rate of the passive humus pool | real | 1/day | — | — |
| [r_hs_rate](r_hs_rate.md) | Daily transformation rate of the slow humus pool | real | 1/day | — | — |
| [r_microb_rate](r_microb_rate.md) | Daily transformation rate of the microbial pool (used on row 2 only) | real | 1/day | — | — |
| [r_meta_rate](r_meta_rate.md) | Daily transformation rate of the metabolic litter pool | real | 1/day | — | — |
| [r_str_rate](r_str_rate.md) | Daily transformation rate of the structural litter pool | real | 1/day | — | — |
| [r_microb_top_rate](r_microb_top_rate.md) | Daily transformation rate of the microbial pool (used on row 1 only) | real | 1/day | — | — |
| [r_hs_hp](r_hs_hp.md) | Base fraction of transformed slow humus carbon passed to the passive pool | real | fraction | — | — |
| [r_a1co2](r_a1co2.md) | Fraction of transformed litter carbon respired as CO2 | real | fraction | — | — |
| [r_asco2](r_asco2.md) | Fraction of transformed slow humus carbon respired as CO2 | real | fraction | — | — |
| [r_apco2](r_apco2.md) | Fraction of transformed passive humus carbon respired as CO2 | real | fraction | — | — |
| [r_abco2](r_abco2.md) | Fraction of transformed microbial carbon respired as CO2 (used on row 1 only) | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
