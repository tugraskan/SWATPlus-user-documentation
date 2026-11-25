---
description: "Harvest export, harvest sink, and plant-kill return"
---

# harvest_sink_kg

**Code reference:** `hpestb_d(j)%pest(ipest)%harvest_sink` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L25)).

The 15-character heading truncates `harvest_sink_kg/ha`. The field starts at zero. The source review found this member in the accumulation and scaling operators and found no direct daily producer. The pesticide database's `harvest_sink` switch is a separate setting. [Record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L25), [Database setting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L21)

**Unit:** kg/ha.

The terminal plant sink removes pesticide from soil at uptake. That mass contributes to the [uptake column](uptake_kg-per-ha.md) and leaves this diagnostic at zero. [Uptake and sink branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L101-L115).

See the [reporting periods](hru-landscape-pesticide-balance.md#reporting-periods) for how the writer aggregates this field.

[Back to schema](hru-landscape-pesticide-balance.md).
