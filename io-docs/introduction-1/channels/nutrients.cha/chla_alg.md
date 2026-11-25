---
description: Ratio of chlorophyll-a to algal biomass
---

# chla\_alg

**Code reference:** `ch_nut(ich)%ai0` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L138)).

Ratio of chlorophyll-a to algal biomass ($\mu\text{g chla}/\text{mg alg}$, default `50.0`, range `10.0–100.0`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L64), values `<= 0.` are replaced with `50.`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L158-L159), SWAT+ converts incoming chlorophyll-a concentration ($\text{chla}_{\text{in}}$, $\text{mg/L}$) to algal biomass concentration ($\text{algcon}$, $\text{mg alg/L}$) and back at [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L232):

$$\text{algcon} = \frac{1000\,\text{chla}_{\text{in}}}{\alpha_0}$$

where $\text{algcon}$ is algal biomass concentration (`mg alg/L`), $\text{chla}_{\text{in}}$ is incoming chlorophyll-a concentration (`mg/L`), and $\alpha_0$ is `chla_alg` ($\mu\text{g chla}/\text{mg alg}$).

It also appears in the algal self-shading expression at [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L162-L164), though light extinction is subsequently capped at `lt_nonalg` ([`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L169)).
