---
description: Depth from mid-slope surface to bottom of aquifer
---

# dep\_bot

**Code reference:** `aqudb(i)%dep_bot` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L9)).

Depth (m) from the mid-slope ground surface to the bottom of the aquifer. Together with [dep\_wt](dep_wt-1.md) and [spec\_yld](spec_yld.md), it sets the initial aquifer storage in [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L174):

$$
S_{0} = 1000 \times (d_{\text{bot}} - d_{\text{wt}}) \times S_{y}
$$

where $S_{0}$ is storage (mm), $d_{\text{bot}}$ is _dep\_bot_ (m), $d_{\text{wt}}$ is [dep\_wt](dep_wt-1.md) (m), and $S_{y}$ is [spec\_yld](spec_yld.md). Each day, [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L106-L107) inverts this relation to update the water-table depth from storage, clamped at 0. _dep\_bot_ should therefore be larger than [dep\_wt](dep_wt-1.md); if they are equal (as with the default values of 10 m), the aquifer starts empty.

_dep\_bot_ also sets the aquifer volume used for constituent initialization from [initial.aqu\_cs](../../initialization/initial.aqu_cs/) ([`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L76)).
