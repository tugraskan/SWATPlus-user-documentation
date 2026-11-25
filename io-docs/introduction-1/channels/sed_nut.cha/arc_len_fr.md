---
description: "Fraction of the channel arc length over which bank erosion is permitted to occur"
---

# arc_len_fr

**Code reference:** `sd_chd1(idb)%arc_len_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L56)).

Intended fraction of the channel arc length over which bank erosion occurs (struct default `1.2`). In [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L211-L214), the routine computes the arc length and protected length:

$$L_{\text{arc}} = 0.25\,L_{\text{ch}}, \qquad L_{\text{prot}} = L_{\text{arc}} \cdot f_{\text{arc}}$$

where $L_{\text{arc}}$ is the channel arc length, $L_{\text{ch}}$ is channel length (`chl`), $L_{\text{prot}}$ is the protected arc length, and $f_{\text{arc}}$ is `arc_len_fr` (dimensionless).

It then calculates bank erosion mass `ebank_t` using the unscaled `arc_len` rather than `prot_len`. From source reading at `6f515368`, `arc_len_fr` has no effect on simulated bank erosion.
