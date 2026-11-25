---
description: Temperature lapse rate
---

# tlaps

**Code reference:** `bsn_prm%tlaps` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L118), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Elevation-based temperature lapse rate (`deg C/km`, struct default `6.5`). When [lapse](../codes.bsn/lapse.md) = `1`, [`cli_lapse.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_lapse.f90#L30-L33) computes the temperature adjustment (`deg C`) added to daily maximum, minimum, and average air temperature in [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L129-L131):

$$\Delta T = \text{tlaps} \cdot \frac{z_{\text{gage}} - z_{\text{obj}}}{1000}$$

where $z_{\text{gage}}$ and $z_{\text{obj}}$ are temperature-gage (or weather-generator) and object elevations (`m`). A positive value denotes a decrease in temperature with an increase in elevation.
