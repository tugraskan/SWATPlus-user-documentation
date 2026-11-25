---
description: Equilibrium sediment concentration in the reservoir
---

# nsed

**Code reference:** `res_sed(ires)%nsed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L100)).

Equilibrium suspended sediment concentration in the water body (`mg/L`, i.e., `ppm`; historical table default: `1.0`, range `1.0–5000.0`; Fortran struct default: `0.`). Enter `nsed` in mg/L; SWAT+ main (`6f515368`) compares it directly with the water body's suspended sediment concentration in ppm and does not convert it to kg/L.

Settling occurs in [`res_sediment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L40-L42) only when the suspended sediment concentration exceeds `nsed`:

$$C_{\text{sed,new}} = \max\!\left(C_{\text{eq}},\; (C_{\text{sed}} - C_{\text{eq}}) \, c_{\text{stl}} + C_{\text{eq}}\right) \quad \text{when } C_{\text{sed}} > C_{\text{eq}}$$

where $C_{\text{sed,new}}$ is the post-settling suspended sediment concentration (mg/L), $C_{\text{sed}}$ is the suspended sediment concentration (mg/L), $C_{\text{eq}}$ is `nsed` (mg/L), and $c_{\text{stl}}$ is the daily settling factor computed from [d50](d50.md) ($\exp(-0.184 \, d_{50})$).
