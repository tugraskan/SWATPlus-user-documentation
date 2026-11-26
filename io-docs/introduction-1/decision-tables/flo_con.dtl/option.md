---
description: "Action option"
---

# option

**Code reference:** `dtbl_flo(i)%act(iac)%option` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L21)).

Variant of the [action type](typ.md). $c_1$ is [const](const.md) and $c_2$ is [const2](const2.md).

| Type | Option | Result |
| ---- | ------ | ------ |
| `wallo_dmd` | `set_dmd` | Sets fixed demand from `const` (`m^3`; see below) |
| `wallo_dmd` | `irr_dmd` | Adds the demand of the place of use given by `ob_num` |
| `wallo_dmd` | `fill_res`, `fill_wtow`, `fill_can` | Computes storage-fill demand for a reservoir, water tower, or canal (see below) |
| `duty_fr` | `fr1` to `fr6` | Sets fraction $c_1$ for source or receiver 1 to 6 |
| `tileflo_control` | `flo_mm`, `max_mm` | Caps tile flow at `const` (see below) |
| `tileflo_control` | `min_mm` | Floors tile flow at `const` (see below) |
| `tileflo_control` | `all_flo`, `zero_flo`, `frac` | Passes $q$, sets `0`, or scales tile flow by `const` (see below) |

For `wallo_dmd` with `set_dmd`:

$$D = c_1$$

where $D$ is demand (`m^3`) and $c_1$ is `const` (`m^3`).

For `wallo_dmd` with `fill_res`, `fill_wtow`, or `fill_can`:

$$D = \max\big(0,\; (c_1 V - S)\,c_2\big)$$

where:
- $D$ is fill demand (`m^3`),
- $c_1$ is `const` (target storage fraction, dimensionless),
- $V$ is reservoir, water tower, or canal storage capacity (`m^3`),
- $S$ is current storage (`m^3`), and
- $c_2$ is `const2` (multiplier, dimensionless).

For `tileflo_control` with `flo_mm` or `max_mm`:

$$q_{\text{out}} = \min(q,\; c_1)$$

where $q_{\text{out}}$ is controlled tile flow (`mm`), $q$ is simulated tile flow (`mm`), and $c_1$ is `const` (`mm`).

For `tileflo_control` with `min_mm`:

$$q_{\text{out}} = \max(q,\; c_1)$$

where $q_{\text{out}}$ is controlled tile flow (`mm`), $q$ is simulated tile flow (`mm`), and $c_1$ is `const` (`mm`).

For `tileflo_control` with `frac`:

$$q_{\text{out}} = c_1\,q$$

where $q_{\text{out}}$ is controlled tile flow (`mm`), $c_1$ is `const` (dimensionless), and $q$ is simulated tile flow (`mm`).

Sources: [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L190-L240) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L833-L889)
