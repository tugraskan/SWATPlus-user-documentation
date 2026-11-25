---
description: "Ratio of peak to mean daily flow in the channel"
---

# pk_rto

**Code reference:** `sd_chd1(idb)%pk_rto` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L48)).

Ratio of peak to mean daily flow in the channel ($r_{\text{pk}}$, struct default `1.0`). In [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L85-L86), `pk_rto` scales the Fuller–Peck peak-to-mean flow ratio used to compute daily peak flow rate $Q_{\text{peak}}$ (`m3/s`):

$$Q_{\text{peak}} = r_{\text{pk}} \cdot \left(1 + 2.66\left(\frac{A}{100}\right)^{-0.3}\right) \frac{Q}{86400}$$

where $A$ is drainage area (`ha`) and $Q$ is daily inflow volume (`m3/d`).
