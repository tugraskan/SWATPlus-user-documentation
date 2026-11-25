---
description: Denitrification exponential rate coefficient
---

# denit\_exp

**Code reference:** `bsn_prm%cdn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L111), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Exponential rate coefficient controlling daily soil nitrate denitrification when soil water exceeds the threshold [denit\_frac](denit_frac.md) (default `1.4`, range `0–3`; values `< 1.e-6` are reset to `1.40` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L33)).

In [`nut_nminrl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L198-L199) (and [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L438-L439) when [carbon](../codes.bsn/carbon.md) = `2`), daily denitrification (`kg N/ha`) in soil layer $k$ is:

$$N_{\text{denit}} = \text{NO}_{3,k}\left(1 - \exp\!\left(-\text{cdn}\cdot f_T \cdot \frac{\text{OC}_k}{100}\right)\right)$$

where $f_T$ is the temperature cycling factor and $\text{OC}_{k}$ is layer organic carbon (`%`).

<figure><img src="../../../.gitbook/assets/image (9).png" alt="" width="485"><figcaption><p>Impact of denit_exp value on amount of nitrogen lost to denitrification assuming initial nitrate content in layer is 200 kg/ha, temperature of layer is 10ºC, and organic carbon content of layer is 2%.</p></figcaption></figure>
