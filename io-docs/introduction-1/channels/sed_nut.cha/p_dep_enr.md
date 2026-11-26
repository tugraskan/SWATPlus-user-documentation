---
description: "Enrichment factor for phosphorus in the remaining water after deposition"
---

# p_dep_enr

**Code reference:** `sd_chd1(idb)%p_dep_enr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L55)).

Enrichment factor for particulate phosphorus in deposition (struct default `0.5`). On SWAT+ dev it multiplies the floodplain trap efficiency, the overbank fraction and the incoming `sedp` ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L156)), and also the in-channel deposition of the eroded bank load ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L267-L271)). The SWAT+ main form was:

$$P_{\text{sed,fp}} = E_{\text{trap}} \cdot f_{\text{P,enr}} \cdot P_{\text{sed,in}}$$

where $P_{\text{sed,fp}}$ is floodplain-deposited particulate phosphorus (`kg`), $E_{\text{trap}}$ is floodplain sediment trap efficiency (fraction), $f_{\text{P,enr}}$ is `p_dep_enr` (dimensionless), and $P_{\text{sed,in}}$ is incoming particulate phosphorus (`kg`).

At [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L270), it multiplies channel deposition of bank-eroded particulate phosphorus:

$$P_{\text{sed,ch}} = f_{\text{P,enr}} \cdot f_{\text{wb}} \cdot P_{\text{sed,bank}}$$

where $P_{\text{sed,ch}}$ is channel-deposited particulate phosphorus (`kg`), $f_{\text{P,enr}}$ is `p_dep_enr` (dimensionless), $f_{\text{wb}}$ is `wash_bed_fr` (fraction), and $P_{\text{sed,bank}}$ is eroded bank particulate phosphorus (`kg`).
