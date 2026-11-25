---
description: "Groundwater balance residual relative to ending storage"
---

# error

**Code reference:** `mass_error` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L863)).

The daily percentage diagnostic is computed before the m3-to-mm conversion:

`error = 100 * (1 - (vbef + sum_of_signed_fluxes) / vaft)`.

Its denominator is ending groundwater storage, not starting storage, total inflow, or storage change. The signed sum includes recharge, ET, groundwater/channel exchanges, saturation excess, soil transfer, lateral and boundary flow, actual pumping diagnostics, tile flow, reservoir/wetland/canal/floodplain/pond exchange, and phreatophyte uptake. It excludes `pump_def`, because unmet demand is not water actually withdrawn.

**Unit:** %.

Channel exchange changes cell head and storage directly. If those exchanges have already changed `vbef`, the formula still adds `gw_sw` and `sw_gw`. The solver leaves these fields out of its source/sink sum because the exchange routine applies them directly. This timing can contribute to the reported error. [Channel exchange](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L101), [Solver source/sink sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L214)

The expression has no zero-denominator guard at this calculation; its percentage is undefined when `vaft` is zero. Its numerical behavior also depends on the source checkpoints and flux diagnostics described in the [daily schema](daily-basin-water-balance.md); it is not evidence that all exchanges were counted correctly.

This field appears only in the daily basin file. It is not an additional water flux or a longer-period balance-error column.

[Back to the daily basin water-balance schema](daily-basin-water-balance.md).
