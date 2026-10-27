---
description: Outcome
---

# outcome

**Code reference:** `dtbl_lum(i)%act_outcomes(iac,ial)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/conditional_module.f90#L38)).

The outcome determines whether or not an action will be triggered when the condition alternative is met. There has to be an outcome defined for each alternative.&#x20;

The only options for action entries are yes ("y") and no ("n").&#x20;

* If all conditions specified by an alternative are met and the outcome is "y", then the associated action will be performed.&#x20;
* If all conditions specified by an alternative are met but the outcome is "n", the associated action will not be performed.&#x20;
* If not all conditions specified by an alternative are met, the associated action will not be performed, even if the outcome is "y".
