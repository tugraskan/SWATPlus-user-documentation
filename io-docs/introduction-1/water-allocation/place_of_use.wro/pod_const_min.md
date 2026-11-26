---
description: "Fixed minimum level or threshold for withdrawal"
---

# const_min (POD)

**Code reference:** `pou(ipou)%pod(ipod)%const_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L97)).

Fixed minimum withdrawal threshold (default: `0.`). Evaluated by source type in [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L61-L124):

- `wtow` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L62-L64)): minimum fraction of current water-tower storage.
- `cha` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L76-L78)): minimum channel daily flow volume (`m^3`), compared directly against `ht2%flo` (no `86400` multiplier is applied).
- `can` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L89-L91)): minimum fraction of current canal storage.
- `res` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L101-L103)): minimum fraction of principal reservoir volume.
- `aqu` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L113)): maximum allowable water-table depth (`m`); withdrawal proceeds only when $d_{\text{wt}} < c_{\min}$, where $d_{\text{wt}}$ is water-table depth (`m`) and $c_{\min}$ is `const_min` (`m`).

For `wtow`, `can`, and `res`, the minimum retained storage volume is:

$$V_{\min} = c_{\min} \cdot V_{\text{ref}}$$

where $V_{\min}$ is the minimum retained volume ($\text{m}^3$), $c_{\min}$ is `const_min` (fraction), and $V_{\text{ref}}$ is current water-tower storage (`wtow`), current canal storage (`can`), or principal reservoir volume (`res`, $\text{m}^3$).
