---
description: Phosphorus enrichment ratio for loading with sediment
---

# orgp\_enrich

**Code reference:** `hyd_db(ithyd)%erorgp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L15)).

Dimensionless enrichment ratio for sediment-attached phosphorus, including organic and mineral forms. SWAT+ uses the input when it exceeds 0.001 and uses the calculated enrichment ratio otherwise. [`nut_psed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_psed.f90#L63-L79) calculates:

$$P_{\mathrm{sed}} = \frac{1000 \, P_1 R Y}{M_1 A}$$

where:

- $P_{\mathrm{sed}}$ is the sediment-attached phosphorus yield (kg P/ha),
- $P_1$ is the surface soil sediment-attached P pool per hectare (kg P/ha),
- $R$ is the selected enrichment ratio (`orgp_enrich` when above 0.001, dimensionless),
- $Y$ is sediment yield (tonnes),
- $M_1$ is surface-layer soil mass per hectare, and
- $A$ is HRU area (ha).
