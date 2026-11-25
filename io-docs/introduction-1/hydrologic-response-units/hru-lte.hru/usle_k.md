---
description: USLE soil erodibility factor K
---

# usle\_k

**Code reference:** `hlt_db(i)%uslek` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L47)).

USLE soil erodibility factor K. It is one term of the MUSLE factor used for sediment yield ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L244-L245), [`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L359)):

$$F = 11.8 \times K \times C \times P \times LS$$

where:
* $F$ is the combined MUSLE factor,
* $K$ is `usle_k`,
* $C$ is the USLE cover factor ([`usle_c`](usle_c.md)),
* $P$ is the USLE support practice factor ([`usle_p`](usle_p.md)), and
* $LS$ is the USLE slope length and slope factor ([`usle_ls`](usle_ls.md)).
