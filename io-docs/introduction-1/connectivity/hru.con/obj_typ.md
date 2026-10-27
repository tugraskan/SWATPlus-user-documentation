---
description: Type of the receiving object
---

# obj\_typ

**Code reference:** `ob(i)%obtyp_out(isp)`

**Declared type:** `object_connectivity` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hyd_read_connect.f90#L298), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L366)).

The table below lists the spatial objects that can be receiving objects and their respective character codes for specifying the type of receiving object. Recall, Export Coefficient, and Delivery Ratio objects cannot be receiving objects.

| Spatial object | Code  |
| -------------- | ----- |
| HRU            | hru   |
| HRU-lte        | hlt   |
| Routing Unit   | ru    |
| Aquifer        | aqu   |
| Channel        | cha   |
| Reservoir      | res   |
| Outlet         | out   |
