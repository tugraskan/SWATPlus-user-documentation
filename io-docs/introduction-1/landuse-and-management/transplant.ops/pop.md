---
description: "Plant population"
---

# pop

**Code reference:** `transpl(ic)%pop` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L160)).

Plant population in plants per square meter. It is used in the potential-LAI calculation; below 1e-6 the database blai value is used, otherwise the population response curve applies.
