---
description: "Harvest export, harvest sink, and plant-kill return"
---

# harv_export_kg/

**Code reference:** `hpestb_d(j)%pest(ipest)%harv_export` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L24)).

Pesticide removed with harvested plant material in the biomass, grain, or tuber routines. Biomass and tuber harvest also add remaining internal pesticide routed to the terminal sink, when present. [Biomass harvest](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L58-L96), [Grain harvest](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvgrain.f90#L65-L78), [Tuber harvest](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvtuber.f90#L69-L96).

**Unit:** kg/ha.

The 15-character heading truncates `harv_export_kg/ha`. The period writers apply the harvest-field divisors described in the [reporting periods](hru-landscape-pesticide-balance.md#reporting-periods). [Header declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L74)

[Back to schema](hru-landscape-pesticide-balance.md).
