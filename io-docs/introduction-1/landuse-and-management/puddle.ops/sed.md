---
description: "Sediment concentration after puddling"
---

# sed

**Code reference:** `pudl_db(ic)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L20), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_puddle.f90#L42)).

Suspended sediment concentration ($C_{\text{sed}}$, `ppm`, struct default `0.0`) set in standing HRU wetland/paddy water upon puddling. In [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L600) and [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L974), SWAT+ converts this concentration to suspended sediment mass $M_{\text{sed}}$ (`t`):

$$M_{\text{sed}} = \frac{C_{\text{sed}} \cdot V_{\text{wet}}}{10^6}$$

where $V_{\text{wet}}$ is the standing water volume `wet(j)%flo` (`m^3`).
