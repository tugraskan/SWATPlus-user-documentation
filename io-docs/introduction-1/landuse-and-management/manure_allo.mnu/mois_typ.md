---
description: "Manure moisture-type selector"
---

# mois\_typ

**Code reference:** `mallo(imro)%src(i)%mois_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L27), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L67)).

Character string (`len=3`, default `""`, e.g., `wet` or `dry`) identifying the manure moisture state. In SWAT+ main (`6f515368`), `mois_typ` is printed in manure source and demand output files ([`manure_source_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_source_output.f90#L20), [`manure_demand_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_demand_output.f90#L24)) but does not enter allocation or nutrient-application calculations.
