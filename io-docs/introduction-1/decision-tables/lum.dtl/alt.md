---
description: Alternative
---

# alt

**Code reference:** `dtbl_lum(i)%alt(ic,ial)`

**Declared type:** `decision_table` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/dtbl_lum_read.f90#L70), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/conditional_module.f90#L34)).

The alternative is the final piece to construct the “if” statement needed to implement the associated rule. One of the alternative operators listed in the table below must be specified for each condition defined in the Decision Table. The user can define as many alternatives as needed by adding the required number of alt columns and numbering them sequentially (alt1, alt2,...).&#x20;

The model checks if the condition is met by:&#x20;

1. comparing the condition variable to lim\_const (if the condition variable has a limit constant but no limit variable and operator),&#x20;
2. comparing the condition variable to lim\_var (if the condition variable has a limit variable but no limit operator and constant),
3. comparing the condition variable to lim\_var multiplied by/plus/minus/divided by lim\_const (if the condition variable has a limit variable, operator, and constant), or
4. checking if the conditional variable is true (plant\_gro, tile\_drained, and plant\_com).

How the condition variable is compared to 1., 2., or 3. or checked for 4. is controlled by the alternative operator:

| Alternative operator | Description                                                               |
| -------------------- | ------------------------------------------------------------------------- |
| -                    | Condition not relevant                                                    |
| =                    | Condition met if var equals 1., 2., or 3. or if var is true (4.)          |
| /                    | Condition met if var does not equal 1., 2., or 3. or if var is false (4.) |
| >=                   | Condition met if var is larger than or equals 1., 2., or 3.               |
| <=                   | Condition met if var is smaller than or equals 1., 2., or 3.              |
| >                    | Condition met if var is larger than 1., 2., or 3.                         |
| <                    | Condition met if var is smaller than 1., 2., or 3.                        |
