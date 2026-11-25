---
description: "Fraction of bank erosion material that is transported as washload rather than bedload"
---

# wash_bed_fr

**Code reference:** `sd_chd1(idb)%wash_bed_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L58)).

Struct comment ([`sd_channel_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L58)) describes `wash_bed_fr` (default `0.1`) as the washload fraction of bank erosion. However, in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L267-L271), SWAT+ multiplies `bank_ero` by `wash_bed_fr` to compute **channel deposition**, which is subtracted from `ht1`:

$$M_{\text{sed,ch}} = f_{\text{wb}} \cdot M_{\text{sed,bank}}$$

where $M_{\text{sed,ch}}$ is channel-deposited sediment (`t`), $f_{\text{wb}}$ is `wash_bed_fr` (fraction), and $M_{\text{sed,bank}}$ is eroded bank sediment (`t`).

At [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L289), it also multiplies `ebtm_t` into `bed_ero%sed` (whose addition to `ht1` at [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L298) is commented out).
