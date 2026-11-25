---
description: "Water requested by a place of use or by one of its points of diversion"
---

# duty

**Code reference:** `poud_met(ipou)%duty_tot%duty` (MET) and `poud_met(ipou)%pod(ipod)%duty` (POD) ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L112-L126)), printed by [daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L49), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L85-L105), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L143-L163), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L198-L218).

**Unit:** m³. The units line prints `ha-m`, but the value is a volume in m³ and is printed without conversion.

- **MET row:** the POU's duty for the period. For most POU types this is `rate_max × 86400`, or the result of the POU's maximum-demand decision table capped at that value ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L149-L164)). For an irrigation POU it is replaced by the sum of the HRU irrigation demands evaluated during delivery ([`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L36-L101)).
- **POD row:** the POU duty from the start of the day times this POD's fraction ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L166-L186)).

Monthly and yearly values are sums; see the yearly double-counting note under [Reporting periods](allocation-transactions.md#reporting-periods). Average-annual values divide the accumulated totals by the number of printed years.

[Back to the allocation-transactions schema](allocation-transactions.md).
