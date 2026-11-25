---
description: Surface fraction
---

# surf\_frac

**Code reference:** `chemapp_db(ichemapp)%surf_frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L104), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_chemapp.f90#L45)).

Dimensionless fraction (`0.0–1.0`, default `0.0`) of applied chemical placed into soil layer 1 (upper `10 mm`), with the remainder $(1 - f_{\text{surf}})$ placed into soil layer 2.

**Fertilizer, manure, salts, and general constituents:** Applied directly to soil layer 1 by $f_{\text{surf}}$ and soil layer 2 by $(1 - f_{\text{surf}})$ in [`pl_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert.f90#L75-L77), [`pl_manure.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_manure.f90#L73-L75), [`salt_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert.f90#L40-L42), and [`cs_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert.f90#L39-L41).

**Pesticides:** Splits the non-foliar-intercepted pesticide mass $(1 - g_c)\,M_{\text{pest}}$ between soil layers 1 and 2 in [`pest_apply.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_apply.f90#L52-L54):

$$\Delta P_{1} = (1 - g_c)\,f_{\text{surf}}\,M_{\text{pest}}, \qquad \Delta P_{2} = (1 - g_c)\,(1 - f_{\text{surf}})\,M_{\text{pest}}$$

where:
- $\Delta P_{1}$ is pesticide mass added to soil layer 1 (`kg/ha`),
- $\Delta P_{2}$ is pesticide mass added to soil layer 2 (`kg/ha`),
- $g_c$ is the foliar canopy cover fraction (dimensionless),
- $f_{\text{surf}}$ is `surf_frac` (dimensionless), and
- $M_{\text{pest}}$ is total applied pesticide mass (`kg/ha`).

**Ponded wetland/paddy fertilization:** In decision-table fertilization actions ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L376-L377)), when ponded water exists (`wet(j)%flo > 0.`) and `surf_frac == 1`, fertilizer is added directly to ponded water via [`pl_fert_wet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert_wet.f90#L63).
