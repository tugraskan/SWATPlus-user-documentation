---
description: "Running net change in dissolved soil salt from chemistry"
---

# dssl_total

**Code reference:** `ru_hru_saltb_d(iru)%salt(1)%diss` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L10)).

The daily value accumulates signed net changes in dissolved salt from soil chemistry across full HRUs, weighted by their areas. The daily, monthly, and yearly accumulators for this field carry their values forward. Each longer period adds the shorter period's running sum, so earlier changes can be counted repeatedly. The average-annual field has no year division. [HRU chemistry](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L361-L369), [Routing-unit accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L183-L185), [Reporting periods](routing-unit-salt-balance.md#reporting-periods)

**Unit:** kg.

See [reporting periods](routing-unit-salt-balance.md#reporting-periods) for aggregation.

[Back to schema](routing-unit-salt-balance.md).
