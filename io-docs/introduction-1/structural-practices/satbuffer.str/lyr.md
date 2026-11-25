---
description: "Receiving soil-layer index"
---

# lyr

**Code reference:** `satbuff_db(ibuff)%lyr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L104)).

Used directly as the receiving HRU's soil-layer index for tile water and nitrate ([`rls_routetile.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rls_routetile.f90#L31-L33)). Select a layer that exists in the receiving HRU; the inspected routing routine does not implement a separate surface branch for zero. The subsurface portion of the incoming flow is added to layer $l$ as:

$$SW_l \leftarrow SW_l + Q_{\text{buf}}(1 - f_{\text{surf}}), \qquad \text{NO}_{3,l} \leftarrow \text{NO}_{3,l} + N_{\text{buf}}(1 - f_{\text{surf}})$$

where $l$ is `lyr`, $SW_l$ and $\text{NO}_{3,l}$ are soil water and nitrate in layer $l$ of the receiving HRU, $Q_{\text{buf}}$ and $N_{\text{buf}}$ are incoming buffer water and nitrate, and $f_{\text{surf}}$ is the overland fraction (`tile_fr_surf`).
