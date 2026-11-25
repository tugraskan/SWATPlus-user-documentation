---
description: USLE support practice factor P
---

# usle\_p

**Code reference:** `hlt_db(i)%uslep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L49)).

USLE support practice factor P. It is one term of the MUSLE factor used for sediment yield ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L244-L245), [`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L359)):

$$F = 11.8 \times K \times C \times P \times LS$$

where:
* $F$ is the combined MUSLE factor,
* $K$ is the USLE soil erodibility factor ([`usle_k`](usle_k.md)),
* $C$ is the USLE cover factor ([`usle_c`](usle_c.md)),
* $P$ is `usle_p`, and
* $LS$ is the USLE slope length and slope factor ([`usle_ls`](usle_ls.md)).
