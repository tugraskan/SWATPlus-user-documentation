---
description: Type of hydrograph that is sent to the receiving object
---

# hyd\_typ

**Code reference:** `ob(i)%htyp_out(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L372)).

The types of hydrographs that can be sent depend on the sending object. The code tot is used for several spatial objects, but its meaning differs between objects. The table below lists the available codes and their definition depending on the type of object.

| Code | Object                    | Definition                                  |
| ---- | ------------------------- | ------------------------------------------- |
| tot  | Channel                   | Streamflow                                  |
| tot  | Aquifer                   | Groundwater return flow                     |
| tot  | Reservoir                 | Reservoir outflow                           |
| tot  | Outlet                    | Flow at the outlet                          |
| tot  | Recall                    | Flow from point source or inlet             |
| tot  | Export Coefficient        | Export-coefficient hydrograph               |
| tot  | Delivery Ratio            | Hydrograph after the delivery ratios        |
| tot  | HRU-lte                   | Total outflow of the HRU-lte                |
| tot  | HRU, Routing Unit         | Surface runoff + lateral flow + tile flow   |
| sur  | HRU, Routing Unit         | Surface runoff                              |
| lat  | HRU, Routing Unit         | Lateral flow                                |
| til  | HRU, Routing Unit         | Tile flow                                   |
| rhg  | HRU, Routing Unit, Aquifer | Seepage that recharges the receiving object |

Reservoirs, channels, HRU-lte, recall, export-coefficient, delivery-ratio and outlet objects fill only `tot`. In SWAT+ main (6f515368), `rhg` from a reservoir or channel sends nothing ([reservoir outflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L236), [disabled channel recharge](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L496)).

{% hint style="warning" %}
SWAT+ [recognizes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L281-L292) only `tot`, `rhg`, `sur`, `lat` and `til`, and gives no warning for any other code.
{% endhint %}
