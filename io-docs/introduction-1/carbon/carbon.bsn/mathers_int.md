---
description: "Flag selecting the Mathers method for the initial passive humus pool"
---

# mathers\_int

**Code reference:** `org_frac%mathers_method` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L132), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L82), [conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L91-L92)).

`1` sets the initial passive humus carbon from clay and silt content and makes the slow pool take the remainder ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L182-L222)). Any other value uses [frac\_hum\_passive](frac_hum_passive.md) and [frac\_hum\_slow](frac_hum_slow.md).

$$
P = \begin{cases} 0.41 + 0.0053 \, S & S \ge 35 \\ 0.069 + 0.015 \, S & S < 35 \end{cases}, \qquad f_{pass} = \min\left(\frac{P}{OC}, \; 0.96\right)
$$

$$
C_{pass} = f_{pass} \, C_{tot}, \qquad C_{slow} = (1 - f_{pass} - f_{mic} - f_{lit}) \, C_{tot}, \qquad C_{mic} = f_{mic} \, C_{tot}
$$

where:

- $S$ is the layer's clay + silt content (%),
- $P$ is the passive humus carbon as a percent of soil mass (%),
- $OC$ is the layer's organic carbon content from `soils.sol` (%),
- $f_{pass}$ is the passive share of the layer's organic carbon (fraction),
- $f_{mic}$ is [frac\_hum\_microb](frac_hum_microb.md) (fraction),
- $f_{lit}$ is [frac\_litter](frac_litter.md) (fraction),
- $C_{pass}$, $C_{slow}$ and $C_{mic}$ are the initial passive, slow and microbial carbon (kg/ha), and
- $C_{tot}$ is the layer's organic carbon (kg/ha).

The passive pool is not scaled by $1 - f_{lit}$; the litter share comes out of the slow pool instead. Pool masses are carbon / 0.58. `frac_hum_passive` and `frac_hum_slow` from this file have no effect when `mathers_int = 1`.

{% hint style="info" %}
In SWAT+ main the threshold compared clay + silt (in percent) with 0.35, so the second equation was never used. On dev the threshold is 35.
{% endhint %}

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `mathers_method` and uses 1.
