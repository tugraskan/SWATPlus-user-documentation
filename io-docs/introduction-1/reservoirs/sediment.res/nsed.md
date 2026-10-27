---
description: Equilibrium sediment concentration in the reservoir
---

# nsed

**Code reference:** `res_sed(ires)%nsed`

**Declared type:** `reservoir_sed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_sed.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L100)).

The amount of suspended solid settling that occurs in the water body on a given day is calculated as a function of concentration. Settling occurs only when the sediment concentration in the water body exceeds the equilibrium sediment concentration specified by the user.

Enter `nsed` in mg/L (ppm). SWAT+ main (6f515368) compares it directly with the water body's sediment concentration in ppm; it does not convert the input to kg/L.
