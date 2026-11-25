---
description: Clay content of channel bank and bed
---

# clay

**Code reference:** `sd_chd(idb)%ch_clay` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L32)).

Clay content of the channel bank and bed material, entered in percent (`%`, default `50.00`, range `0–100`).

In [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L169-L175), `clay` controls soil bank cohesion $C$ (floored at $1000$ for sandy soils) used in the bank critical velocity calculation:

$$C = \max\!\left(1000,\; -87.1 + 42.82\,\text{clay} - 0.261\,\text{clay}^2 + 0.029\,\text{clay}^3\right)$$

where $C$ is soil bank cohesion (floored at $1000$) and $\text{clay}$ is `clay` (`%`).

The routine also computes the bank-erosion exponent `b_exp` from `clay` ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L184-L185)), though the commented-out power equation at [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L195) leaves `b_exp` unused.
