# cal\_parms.cal

{% hint style="info" %}
This file should not be modified by the user.
{% endhint %}

The second line contains the number of parameter records that follow.

| Field    | Description                      | Type   |
| -------- | -------------------------------- | ------ |
| name     | Name of the parameter            | string |
| obj\_typ | Object impacted by the parameter | string |
| abs\_min | Minimum allowed parameter value after a calibration change | real |
| abs\_max | Maximum allowed parameter value after a calibration change | real |
| units | Unit of the parameter | string |

SWAT+ main (6f515368) reads and stores the units text, but does not use it in a calculation or condition.
