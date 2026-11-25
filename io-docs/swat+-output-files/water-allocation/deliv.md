---
description: "Water recorded as delivered to a place of use or withdrawn by a point of diversion"
---

# deliv

**Code reference:** `poud_met(ipou)%duty_tot%deliv` (MET) and `poud_met(ipou)%pod(ipod)%deliv` (POD) ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L112-L126)), printed by [daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L49), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L85-L105), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L143-L163), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L198-L218).

**Unit:** m³. The units line prints `ha-m`, but the value is a volume in m³ and is printed without conversion.

- **MET row:** for most POU types, the sum of the day's withdrawals recorded for the POU after the duty was set ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L141-L143)). For an irrigation POU, the sum of the HRU demands that were supplied ([`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L56-L99)).
- **POD row:** the most recent withdrawal recorded for this POD, not a sum over the day's calls. The POD hydrograph `flo` on the same row does sum them ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L131-L142)).

`duty − deliv` is not a validated unmet demand; see [Withdrawal limits and compensation](allocation-transactions.md#withdrawal-limits-and-compensation).

[Back to the allocation-transactions schema](allocation-transactions.md).
