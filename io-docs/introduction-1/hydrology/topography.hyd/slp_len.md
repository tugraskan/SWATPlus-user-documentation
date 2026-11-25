---
description: Average slope length
---

# slp\_len

**Code reference:** `topo_db(ith)%slope_len` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L8)).

Average overland slope length $L$ in meters, from the start of sheet flow to where runoff concentrates. The built-in record uses 50 m. It enters the overland travel time equation described under [slope steepness](slp.md) and the MUSLE slope-length factor:

$$LS = \left(\frac{L}{22.128}\right)^{m} \left(65.41\,\sin^2\theta + 4.56\,\sin\theta + 0.065\right)$$

$$\theta = \arctan(S), \qquad m = 0.6\left[1 - \exp(-35.835 S)\right]$$

where:

- $LS$ is the MUSLE slope-length factor (dimensionless),
- $L$ is `slp_len` (m),
- $m$ is the slope-length exponent (dimensionless),
- $\theta$ is the slope angle (radians), and
- $S$ is [slope steepness](slp.md) (m/m).

[`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L366-L372)

The initialization calculates a practice-based maximum slope length in a temporary variable, but the LS equation still uses the full HRU slope length. [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L366-L372)
