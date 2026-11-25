---
description: "Fraction of soil organic carbon placed in the litter pools at the start"
---

# frac\_litter

**Code reference:** `org_frac%frac_litter` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L128), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L70-L71), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L473-L474)).

Fraction of each layer's initial organic carbon (from the `soils.sol` [carbon](../../soils/soils.sol/carbon.md) column) that [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L224-L234) places in the litter pools: 85% metabolic and 15% structural. Values below 0 are set to 0 and values above 1 to 1 ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L148-L153)). Without the Mathers method, the rest, $1 - f_{lit}$, goes to the humus and microbial pools:

$$
C_{meta} = 0.85 \, f_{lit} \, C_{tot}, \qquad C_{str} = 0.15 \, f_{lit} \, C_{tot}, \qquad C_{pass} = (1 - f_{lit}) \, f_{pass} \, C_{tot}
$$

where:

- $C_{meta}$ is the initial metabolic litter carbon (kg/ha),
- $C_{str}$ is the initial structural litter carbon (kg/ha),
- $C_{pass}$ is the initial passive humus carbon (kg/ha),
- $f_{lit}$ is `frac_litter` (fraction),
- $f_{pass}$ is [frac\_hum\_passive](frac_hum_passive.md) (fraction), and
- $C_{tot}$ is the layer's organic carbon (kg/ha).

The slow and microbial pools use [frac\_hum\_slow](frac_hum_slow.md) and [frac\_hum\_microb](frac_hum_microb.md) in the same way ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L160-L180)). With [mathers\_int](mathers_int.md) `= 1` the passive pool is set from soil texture instead, and the litter share is taken from the slow pool. Enter a fraction between 0 and 1.

{% hint style="warning" %}
This column replaces `frac_seq` from SWAT+ main and holds its complement: `frac_litter` = 1 − `frac_seq`. A main value of 0.95 corresponds to 0.05 here. The source default is 0.05.
{% endhint %}

The calibration parameter is still `init_seq`. It adjusts the non-litter share $1 - f_{lit}$ and stores the result back as `frac_litter` ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L473-L474)). The SWAT+ example file (`refdata/Ames_sub1`) heads this column `init_litter`.
