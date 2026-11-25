---
description: Rate factor for humus mineralization of active organic nutrients (N and P)
---

# orgn\_min

**Code reference:** `bsn_prm%cmn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L87), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Rate coefficient ($c_{\text{mn}}$, table default `0.0003`, range `0.0003–0.003`; struct default `0.003`, values `< 1.e-6` reset to `0.0003` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L14) and copied to each HRU in [`hrudb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hrudb_init.f90#L34)).

When static soil carbon ([carbon](../codes.bsn/carbon.md) = `0`) is active, [`nut_nminrl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L128-L136) computes daily humus mineralization of active organic nitrogen ($N_{\text{min}}$) and linked stable organic phosphorus ($P_{\text{min}}$, `kg/ha`) as:

$$N_{\text{min}} = c_{\text{mn}}\,f_{\text{cs}}\,N_{\text{hact}}, \qquad P_{\text{min}} = 1.4\,N_{\text{min}}\,\frac{P_{\text{hsta}}}{N_{\text{hsta}} + N_{\text{hact}}}$$

where $f_{\text{cs}}$ is the combined temperature and soil-water factor and $N_{\text{hact}}$, $N_{\text{hsta}}$, and $P_{\text{hsta}}$ are active/stable humus N and stable humus P (`kg/ha`).
