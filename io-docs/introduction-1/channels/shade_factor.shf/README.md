# shade_factor.shf

Daily channel shading factors for the water-temperature calculation. Rows are used when the shade-factor switch in temperature.cha is enabled; reading the file itself is not conditional on that switch.

The first line is a title and the second line is a header. Each subsequent record contains the fields below, in this order. There is no separate record-count line.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [jday](jday.md) | Day of year | integer | day of year | — | — |
| [cha](cha.md) | Channel (reach) identifier for the shading entry | integer | n/a | — | — |
| [value](value.md) | Fraction of incoming shortwave radiation blocked by shading | real | fraction | — | — |

Recommended defaults and ranges are not specified by this page. The dash does not imply a default of zero.

The file lookup is used when `w_temp(0)%sf_on == 1`. When the switch is off, the temperature calculation uses `w_temp(0)%ssff`. Provide matching day/channel rows for the ordinary days you intend to simulate; the lookup does not supply a missing-row fallback.
