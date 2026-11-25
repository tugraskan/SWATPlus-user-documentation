---
description: "Record name"
---

# name

**Code reference:** `pestcp(ip)%daughter(imeta)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L28)).

Daughter pesticide name. It must be in `pesticide.pes` and also listed as a simulated pesticide in [constituents.cs](../../constituents/constituents.cs/); otherwise it gets no position in the simulation ([`pest_metabolite_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_metabolite_read.f90#L66-L71)).
