---
description: "Nitrate removed by the first-order aquifer loss calculation"
---

# no3_loss

**Code reference:** `aqu_d(iaq)%no3_loss = no3_init - aqu_d(iaq)%no3_st`, after multiplying stored nitrate by `aqu_prm(iaq)%nloss` ([loss calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L160)).

The nitrate amount removed by this first-order loss step. It excludes the separately reported nitrate carried by groundwater discharge (`no3_lat`) and seepage (`no3_seep`). The retention coefficient is initialized as `Exp(-.693 / (hlife_n + .1))` ([coefficient](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L170)).

**Unit:** kg N/ha in the daily calculation's convention. The stored-nitrate component has initialization/allocation mass-basis inconsistencies; see [no3_st](no3_st.md).

Monthly values sum daily exchanges; yearly values sum the monthly totals. Average-annual values divide the accumulated yearly totals by `time%yrs_prt`.

Basin output applies `aqu_prm(iaq)%area_ha / bsn%area_tot_ha`; the denominator is the full basin area, not the sum of aquifer areas. This is not necessarily a normalized mean over just the aquifers.

[Back to the output table](README.md).
