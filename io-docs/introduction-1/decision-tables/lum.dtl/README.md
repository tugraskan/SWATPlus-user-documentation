---
description: These files contain the Decision Tables.
---

# "name".dtl

The structure of the decision table files is different than that of most other SWAT+ input files. As usual, the first line is reserved for a title. The second line in the file specifies the total number of decision tables included in the file.&#x20;

Each decision table has three parts, which all have their own headers. First, the name of the decision table and the number of conditions, alternatives, and actions are specified.     &#x20;

| Field  | Description                | Type    |
| ------ | -------------------------- | ------- |
| name   | Name of the decision table | string  |
| conds  | Number of conditions       | integer |
| alts   | Number of alternatives     | integer |
| acts   | Number of actions          | integer |

Next, the conditions and alternatives are defined. The number of lines used for this part of the decision table depends on the number of conditions.

<table><thead><tr><th>Field</th><th width="274.3333333333333">Description</th><th>Type</th></tr></thead><tbody><tr><td><a href="var.md">var</a></td><td>Condition variable</td><td>string</td></tr><tr><td><a href="obj.md">obj</a></td><td>Object type</td><td>string</td></tr><tr><td><a href="obj_num.md">obj_num</a></td><td>Object ID</td><td>integer</td></tr><tr><td><a href="lim_var.md">lim_var</a></td><td>Limit variable</td><td>string</td></tr><tr><td><a href="lim_op.md">lim_op</a></td><td>Limit operator</td><td>string</td></tr><tr><td><a href="lim_const.md">lim_const</a></td><td>Limit constant</td><td>real</td></tr><tr><td><a href="alt.md">alt</a></td><td>Alternative</td><td>string</td></tr></tbody></table>

Finally, the outcomes and actions are defined. The number of lines used for this part of the decision table depends on the number of actions.

| Field                    | Description                    | Type    |
| ------------------------ | ------------------------------ | ------- |
| [act\_typ](act_typ.md) | Type of action                 | string  |
| [obj](obj-1.md) | Object type                    | string  |
| [obj\_num](obj_num-1.md) | Object ID                      | integer |
| [name](name.md)          | Name of the action             | string  |
| [option](option.md)      | Action option                  | string  |
| [const](const.md)        | Action constant                | real    |
| [const2](const2.md)      | Action constant                | real    |
| [fp](fp.md) | File pointer for action option | string  |
| [outcome](outcome.md) | Outcome                        | string  |
