---
description: "Surface-water irrigation"
---

# irsw_na

**Code reference:** `ru_hru_saltb_d(iru)%salt(isalt)%irsw` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L19)).

Sodium in the HRU surface-water irrigation diagnostic, converted to kg with the full HRU area. This field stays zero on the inspected revision because the irrigation salt diagnostic has no active producer. [Routing-unit calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L165-L166), [HRU salt inputs](../hru-salt/README.md#irrigation-deposition-applications-and-uptake)

**Unit:** kg.

See [reporting periods](routing-unit-salt-balance.md#reporting-periods) for aggregation.

[Back to schema](routing-unit-salt-balance.md).
