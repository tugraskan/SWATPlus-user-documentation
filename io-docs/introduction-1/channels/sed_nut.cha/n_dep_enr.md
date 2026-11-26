---
description: "Enrichment factor for nitrogen in the remaining water after deposition"
---

# n_dep_enr

**Code reference:** `sd_chd1(idb)%n_dep_enr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L54)).

Enrichment factor for organic nitrogen in deposition (struct default `0.5`). On SWAT+ dev it multiplies the floodplain trap efficiency, the overbank fraction and the incoming `orgn` ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L155)), and also the in-channel deposition of the eroded bank load ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L267-L271)). The SWAT+ main form was:

$$N_{\text{org,fp}} = E_{\text{trap}} \cdot f_{\text{N,enr}} \cdot N_{\text{org,in}}$$

where $N_{\text{org,fp}}$ is floodplain-deposited organic nitrogen (`kg`), $E_{\text{trap}}$ is floodplain sediment trap efficiency (fraction), $f_{\text{N,enr}}$ is `n_dep_enr` (dimensionless), and $N_{\text{org,in}}$ is incoming organic nitrogen (`kg`).

At [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L269), it multiplies channel deposition of bank-eroded organic nitrogen:

$$N_{\text{org,ch}} = f_{\text{N,enr}} \cdot f_{\text{wb}} \cdot N_{\text{org,bank}}$$

where $N_{\text{org,ch}}$ is channel-deposited organic nitrogen (`kg`), $f_{\text{N,enr}}$ is `n_dep_enr` (dimensionless), $f_{\text{wb}}$ is `wash_bed_fr` (fraction), and $N_{\text{org,bank}}$ is eroded bank organic nitrogen (`kg`).
