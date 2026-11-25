---
description: Type of the receiving object
---

# obj\_typ

**Code reference:** `ob(i)%obtyp_out(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L369)).

The table below lists the spatial objects that can be receiving objects and their respective character codes for specifying the type of receiving object. Recall objects cannot be receiving objects. The codes are matched in [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L218-L279).

| Spatial object                 | Code |
| ------------------------------ | ---- |
| HRU                            | hru  |
| HRU-lte                        | hlt  |
| Routing Unit                   | ru   |
| Aquifer                        | aqu  |
| SWAT-DEG channel (chandeg.con) | sdc  |
| SWAT channel (channel.con)     | cha  |
| Reservoir                      | res  |
| Export Coefficient             | exc  |
| Delivery Ratio                 | dr   |
| Outlet                         | out  |

An export-coefficient object takes its outflow from its database record, so a hydrograph sent to it with `exc` does not change that outflow.

{% hint style="warning" %}
SWAT+ gives no warning for a code that is not in this table. GWFlow cells cannot be named as receivers: the code is stored in three characters, so it never matches `gwflow`.
{% endhint %}
