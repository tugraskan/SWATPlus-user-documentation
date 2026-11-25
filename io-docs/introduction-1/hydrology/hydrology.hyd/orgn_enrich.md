---
description: Organic nitrogen enrichment ratio for loading with sediment
---

# orgn\_enrich

**Code reference:** `hyd_db(ithyd)%erorgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L13)).

Dimensionless enrichment ratio for organic nitrogen in eroded surface sediment. SWAT+ uses the input when it exceeds 0.001 and uses the calculated sediment enrichment ratio otherwise. In [`nut_orgn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_orgn.f90#L33-L48), the standard organic-N routine uses:

$$N_{\mathrm{sed}} = \frac{1000 \, N_1 R Y}{M_1 A}$$

where:

- $N_{\mathrm{sed}}$ is the organic nitrogen transported with sediment (kg N/ha),
- $N_1$ is the surface soil organic N pool per hectare (kg N/ha),
- $R$ is the selected enrichment ratio (`orgn_enrich` when above 0.001, dimensionless),
- $Y$ is sediment yield (tonnes),
- $M_1$ is the surface layer soil mass per hectare, and
- $A$ is HRU area (ha).
