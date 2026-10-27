# cal\_parms.cal

{% hint style="info" %}
This file should not be modified by the user.
{% endhint %}

The second line contains the number of parameter records that follow.

| Field    | Description                      | Type   |
| -------- | -------------------------------- | ------ |
| name     | Name of the parameter            | string |
| obj\_typ\* | Object impacted by the parameter | string |
| abs\_min\* | Minimum allowed parameter value after a calibration change | real |
| abs\_max\* | Maximum allowed parameter value after a calibration change | real |
| units | Unit of the parameter | string |

\* Input-file labels marked with an asterisk have different Fortran names: `obj_typ` → `cal_parms(i)%ob_typ`; `abs_min` → `cal_parms(i)%absmin`; `abs_max` → `cal_parms(i)%absmax`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cal_parm_read.f90#L42).

SWAT+ main (6f515368) reads and stores the units text, but does not use it in a calculation or condition.
