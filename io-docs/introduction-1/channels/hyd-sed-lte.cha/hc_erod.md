---
description: Nitrogen concentration in channel bank and bed
---

# n\_conc

**Code reference:** `sd_chd(idb)%n_conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L39)).

Nitrogen concentration in channel bank and bed material, entered in mg/kg (default `0.10`). SWAT+ uses it in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L241) to calculate organic nitrogen associated with eroded bank sediment:

$$N_{\text{org,bank}} = \frac{M_{\text{sed,bank}} \cdot C_{\text{N}}}{1000}$$

where $N_{\text{org,bank}}$ is organic nitrogen in eroded bank sediment (`kg`), $M_{\text{sed,bank}}$ is eroded bank sediment (`t`), and $C_{\text{N}}$ is `n_conc` (`mg/kg`).

A matching bed-erosion computation at [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L291) is not added to `ht1` because [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L298) is commented out.
