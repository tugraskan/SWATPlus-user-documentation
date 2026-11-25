---
description: "Release equation"
---

# option

**Code reference:** `dtbl_res(i)%act(iac)%option` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L21)).

Selects the release equation. Eligible rows are processed in order. $c_1$ is [const](const.md), $c_2$ is [const2](const2.md), $S$ is current storage, $V_p$ and $V_e$ are principal and emergency storage, and $I$ is the day's inflow, all in m³. An unrecognized option releases nothing and gives no warning. [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L101-L106)

| Option | Daily release | Source |
| ------ | ------------- | ------ |
| `rate` | Fixed release rate from $c_1$ (m³/s) | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L104-L106) |
| `rate_pct` | Percentage $c_1$ of principal storage $V_p$ | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L108-L110) |
| `inflo_rate` | Inflow plus offset $c_2$, floored by $c_1$ | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L112-L114) |
| `inflo_frac` | Fraction $c_1$ of daily inflow $I$ | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L116-L118) |
| `ab_emer` | Storage above emergency volume $V_e$ when $S > V_e$ | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L120-L122) |
| `days` | Drawdown over $c_1$ days above base $b$ from [file_pointer](file_pointer.md) (`0`, $c_2 V_p$, or $c_2 V_e$) | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L124-L135) |
| `dyrt` | Drawdown over $c_1$ days plus $c_2$ percent of $V_p$, with base $b$ (`0`, $V_p$, or $V_e$) | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L139-L152) |
| `dyrt1` | As `dyrt`, but $b$ is built from condition row 5, 4, or 3 (`con1`, `con2`, `con3`) | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L154-L180) |
| `inflo_targ` | Release to meet target storage $V_p c$, where $c$ is `lim_const` of condition row $c_1$ | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L182-L188) |
| `weir` | Weir equation using the named [weir.res](../../reservoirs/weir.res/README.md) record | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L190-L227) |
| `meas` | Measured flow from the named recall record | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L229-L240) |
| `natlake` | Natural-lake power-law outflow above threshold $s_0$ | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L242-L251) |
| `nonirr-h06` | Hanazaki scheme for non-irrigation reservoirs; $c_1$ is its alpha | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L253-L287) |
| `irr-h06` | Hanazaki scheme for irrigation reservoirs; $c_1$ is alpha, $c_2$ is beta | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L289-L328) |
| `hydrop` | Hydropower scheme; $c_1$ and $c_2$ are the seasonal amplitude and phase | [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L330-L343) |

**`rate`:**

$$R = 86400\,c_1$$

where $R$ is daily release (`m^3`) and $c_1$ is `const` (`m^3/s`).

**`rate_pct`:**

$$R = \frac{c_1\,V_p}{100}$$

where $R$ is daily release (`m^3`), $c_1$ is `const` (`%`), and $V_p$ is principal storage (`m^3`).

**`inflo_rate`:**

$$R = \max(I + 86400\,c_2,\; 86400\,c_1)$$

where $R$ is daily release (`m^3`), $I$ is daily inflow (`m^3`), $c_1$ is `const` (minimum release rate, `m^3/s`), and $c_2$ is `const2` (inflow offset rate, `m^3/s`).

**`inflo_frac`:**

$$R = c_1\,I$$

where $R$ is daily release (`m^3`), $c_1$ is `const` (dimensionless), and $I$ is daily inflow (`m^3`).

**`ab_emer`:** When $S > V_e$,

$$R = S - V_e$$

where $R$ is daily release (`m^3`), $S$ is current storage (`m^3`), and $V_e$ is emergency storage (`m^3`).

**`days`:**

$$R = \frac{S - b}{c_1}$$

where $R$ is daily release (`m^3`), $S$ is current storage (`m^3`), $b$ is the base storage from [file_pointer](file_pointer.md) (`0`, $c_2 V_p$, or $c_2 V_e$, `m^3`), and $c_1$ is `const` (`days`).

**`dyrt` and `dyrt1`:**

$$R = \frac{S - b}{c_1} + \frac{c_2\,V_p}{100}$$

where:
- $R$ is daily release (`m^3`),
- $S$ is current storage (`m^3`),
- $b$ is the base storage (`0`, $V_p$, or $V_e$ for `dyrt`; built from condition rows 5, 4, or 3 for `dyrt1`, `m^3`),
- $c_1$ is `const` (`days`),
- $c_2$ is `const2` (`%`), and
- $V_p$ is principal storage (`m^3`).

**`inflo_targ`:**

$$R = \max(0,\; I + S - V_p\,c)$$

where:
- $R$ is daily release (`m^3`),
- $I$ is daily inflow (`m^3`),
- $S$ is current storage (`m^3`),
- $V_p$ is principal storage (`m^3`), and
- $c$ is `lim_const` of condition row number $c_1$ (dimensionless).

**`natlake`:**

$$s_0 = c_1\,V_p, \qquad s = S - s_0, \qquad R = c_2\,s\left(\frac{s}{V_p - s_0}\right)^{1.5}$$

where:
- $s_0$ is threshold storage (`m^3`),
- $c_1$ is `const` (threshold fraction of principal storage, dimensionless),
- $V_p$ is principal storage (`m^3`),
- $s$ is storage above threshold (`m^3`),
- $S$ is current storage (`m^3`),
- $R$ is daily release (`m^3`), and
- $c_2$ is `const2` (`k`, dimensionless coefficient).

Cautions from source reading at this commit: `natlake` takes a fractional power of a negative number when storage is below $s_0$. `hydrop` computes its seasonal factor without a sine function. `dyrt1` assumes the table has the hard-coded condition row. With more than one time step per day in [time.sim](../../simulation-settings/time.sim/README.md), only `days`, `meas`, and the percentage term of `dyrt`/`dyrt1` are divided by the number of steps, so other options can release several times their daily amount. [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L85-L87)
