---
description: Time threshold used to define dormancy
---

# dorm\_hr

**Code reference:** `bsn_prm%dorm_hr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L116), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Daylength offset threshold (`hours`, table default `0`, range `0–24`; struct default `-1.`) relative to the **minimum** annual daylength ($L_{\min}$) at the station latitude. In [`pl_dormant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_dormant.f90#L29) and [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L119), dormancy begins when current daylength $L_{\text{day}}$ satisfies $L_{\text{day}} - t_{\text{dorm}} < L_{\min}$ and ends when $L_{\text{day}} - t_{\text{dorm}} \ge L_{\min}$ ([`pl_dormant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_dormant.f90#L88)).

When `dorm_hr < 1.e-6`, [`cli_initwgn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L136-L148) automatically computes $t_{\text{dorm}}$ from weather-station latitude $\phi$ (`deg`): `1` hr for $|\phi| > 40^\circ$, `-1` hr for $|\phi| < 20^\circ$, and $(|\phi| - 20)/20$ hr for $20^\circ \le |\phi| \le 40^\circ$.
