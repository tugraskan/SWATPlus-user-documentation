---
description: Object ID
---

# obj\_num

**Code reference:** `dtbl_lum(i)%cond(ic)%ob_num`

**Declared type:** `conditions_var` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/dtbl_lum_read.f90#L70), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/conditional_module.f90#L10)).

If _obj\_num_ = 0, the condition will be checked for the current object of the type specified by [obj](obj.md). If _obj\_num_ > 0, the condition will be checked for the object with the specified ID (in the object's [connect](../../connectivity/hru.con/) file) only.&#x20;

Exception: prob\_unif where obj\_num is the first day of the period.&#x20;
