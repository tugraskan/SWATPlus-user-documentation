---
description: Precipitation lapse rate
---

# plaps

**Code reference:** `bsn_prm%plaps` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L117), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Elevation-based precipitation lapse rate (`mm/km`, struct default `0.`). When [lapse](../codes.bsn/lapse.md) = `1`, [`cli_lapse.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_lapse.f90#L23-L26) computes the precipitation offset (`mm`) added on rainy days in [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L127):

$$\Delta P = \text{plaps} \cdot \frac{z_{\text{obj}} - z_{\text{gage}}}{1000}$$

where $z_{\text{obj}}$ and $z_{\text{gage}}$ are object and precipitation-gage (or weather-generator) elevations (`m`). A positive value increases precipitation with elevation, while a negative value decreases precipitation with elevation.
