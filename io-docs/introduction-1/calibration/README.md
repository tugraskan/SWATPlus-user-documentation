---
description: Input files for hard calibration, soft calibration, and conditional scenario updates in SWAT+.
---

# Calibration

SWAT+ supports **hard calibration** (direct parameter adjustments applied before simulation), **soft calibration** (heuristic annual water-balance, sediment, and plant-growth matching), and **conditional scenario updates** (daily decision-table triggers). Hard and soft calibration files are referenced in the `chg` group of `file.cio` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L78)) and read by [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L14-L35).

## Hard Calibration

{% content-ref url="cal_parms.cal/README.md" %}
[cal_parms.cal](cal_parms.cal/README.md)
{% endcontent-ref %}

{% content-ref url="calibration.cal/README.md" %}
[calibration.cal](calibration.cal/README.md)
{% endcontent-ref %}

## Soft Calibration

{% content-ref url="codes.sft/README.md" %}
[codes.sft](codes.sft/README.md)
{% endcontent-ref %}

{% content-ref url="wb_parms.sft/README.md" %}
[wb_parms.sft](wb_parms.sft/README.md)
{% endcontent-ref %}

{% content-ref url="water_balance.sft/README.md" %}
[water_balance.sft](water_balance.sft/README.md)
{% endcontent-ref %}

{% content-ref url="ch_sed_budget.sft/README.md" %}
[ch_sed_budget.sft](ch_sed_budget.sft/README.md)
{% endcontent-ref %}

{% content-ref url="ch_sed_parms.sft/README.md" %}
[ch_sed_parms.sft](ch_sed_parms.sft/README.md)
{% endcontent-ref %}

{% content-ref url="plant_gro.sft/README.md" %}
[plant_gro.sft](plant_gro.sft/README.md)
{% endcontent-ref %}

{% content-ref url="plant_parms.sft/README.md" %}
[plant_parms.sft](plant_parms.sft/README.md)
{% endcontent-ref %}

## Conditional Scenario Updates

`scen_dtl.upd` is read directly from the simulation working directory by [`cal_cond_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_cond_read.f90#L43-L62) rather than through `file.cio`.

{% content-ref url="scen_dtl.upd/README.md" %}
[scen_dtl.upd](scen_dtl.upd/README.md)
{% endcontent-ref %}
