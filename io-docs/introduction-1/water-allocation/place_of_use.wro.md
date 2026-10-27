# place_of_use.wro

This file defines places of use (POUs), their points of diversion (PODs), and their points of return (PORs). The default filename is `place_of_use.wro`, selected through `in_wallo%pou`.

The reader consumes a title line, an integer number of POUs, and a header line. Each POU then has one main record, followed by `pods` POD records and `pors` POR records. No separate header is skipped inside those repeated records.

These tables give the exact read order and code identifiers in SWAT+ main `6f515368`. They use internal Fortran names; they do not assert Editor header spellings. Array indices are the reader's loop variables. Declared types identify the owning derived type, or the primitive type of a local variable. Descriptions summarize the source declarations. Units in those comments have not been checked against downstream calculations; recommended defaults and ranges are not supplied by this layout reference.

## Place-of-use record

| Position | Field | Code reference | Declared type | Description |
| --- | --- | --- | --- | --- |
| 1 | `ip` | `ip` | `integer` | Place-of-use identifier, first read as ipou to select the array entry. |
| 2 | `name` | `pou(ipou)%name` | `place_of_use` | name of POU |
| 3 | `typ` | `pou(ipou)%typ` | `place_of_use` | type of POU |
| 4 | `typ_num` | `pou(ipou)%typ_num` | `place_of_use` | POU number |
| 5 | `pods` | `pou(ipou)%pods` | `place_of_use` | number of sources or points of diversion (PODs) for the POU |
| 6 | `pors` | `pou(ipou)%pors` | `place_of_use` | number of points of return (PORs) for the POU |
| 7 | `dtbl_mx` | `pou(ipou)%dtbl_mx` | `place_of_use` | decision table name to set max daily right or duty |
| 8 | `rate_max` | `pou(ipou)%rate_max` | `place_of_use` | fixed max daily right or duty (m3/s) - if dtble is not used |
| 9 | `dtbl_pod_fr` | `pou(ipou)%dtbl_pod_fr` | `place_of_use` | decision table name to set fractions from each POD - if null use constant fraction |
| 10 | `dtbl_por_fr` | `pou(ipou)%dtbl_por_fr` | `place_of_use` | decision table name to set fractions to each POR - if null use constant fraction |

## Point-of-diversion record within a POU

| Position | Field | Code reference | Declared type | Description |
| --- | --- | --- | --- | --- |
| 1 | `pp` | `pp` | `character (len=5)` | Record tag read into a local character variable. |
| 2 | `num` | `pou(ipou)%pod(ipod)%num` | `pou_points_of_diversion` | POD number |
| 3 | `name` | `pou(ipou)%pod(ipod)%name` | `pou_points_of_diversion` | name of POD |
| 4 | `typ` | `pou(ipou)%pod(ipod)%typ` | `pou_points_of_diversion` | type of POD - channel, reservoir, aquifer, canal, etc |
| 5 | `num` | `pou(ipou)%pod(ipod)%num` | `pou_points_of_diversion` | POD number |
| 6 | `conv_typ` | `pou(ipou)%pod(ipod)%conv_typ` | `pou_points_of_diversion` | conveyance type - pipe or pump |
| 7 | `conv_num` | `pou(ipou)%pod(ipod)%conv_num` | `pou_points_of_diversion` | number of the conveyance object |
| 8 | `dtbl_min` | `pou(ipou)%pod(ipod)%dtbl_min` | `pou_points_of_diversion` | decision table name to set minimum level of POD for withdrawal |
| 9 | `const_min` | `pou(ipou)%pod(ipod)%const_min` | `pou_points_of_diversion` | fixed min daily level - if dtble is not used |
| 10 | `dtbl_wdraw` | `pou(ipou)%pod(ipod)%dtbl_wdraw` | `pou_points_of_diversion` | decision table name to set maximum withdrawal |
| 11 | `ann_max` | `pou(ipou)%pod(ipod)%ann_max` | `pou_points_of_diversion` | annual maximim withdrawal (m3/s) - if dtbl not used |
| 12 | `frac` | `pou(ipou)%pod(ipod)%frac` | `pou_points_of_diversion` | fraction of daily right from the POD (m3/s) |
| 13 | `comp` | `pou(ipou)%pod(ipod)%comp` | `pou_points_of_diversion` | compensate if unmet (y/n) |

The reader writes positions 2 and 5 into the same `pou(ipou)%pod(ipod)%num` component. The later value replaces the earlier one. Both positions are shown because this is what the reviewed code reads; the separately declared `typ_num` component is not read at position 5.

## Point-of-return record within a POU

| Position | Field | Code reference | Declared type | Description |
| --- | --- | --- | --- | --- |
| 1 | `pp` | `pp` | `character (len=5)` | Record tag read into a local character variable. |
| 2 | `num` | `pou(ipou)%por(ipor)%num` | `pou_points_of_return` | POR number |
| 3 | `name` | `pou(ipou)%por(ipor)%name` | `pou_points_of_return` | name of POR |
| 4 | `typ` | `pou(ipou)%por(ipor)%typ` | `pou_points_of_return` | type of POR |
| 5 | `num` | `pou(ipou)%por(ipor)%num` | `pou_points_of_return` | POR number |
| 6 | `conv_typ` | `pou(ipou)%por(ipor)%conv_typ` | `pou_points_of_return` | conveyance type - pipe or pump |
| 7 | `conv_num` | `pou(ipou)%por(ipor)%conv_num` | `pou_points_of_return` | number of the conveyance object |
| 8 | `dtbl_max` | `pou(ipou)%por(ipor)%dtbl_max` | `pou_points_of_return` | decision table name to set maximum level of POR for return |
| 9 | `const_max` | `pou(ipou)%por(ipor)%const_max` | `pou_points_of_return` | fixed max daily level - if dtble is not used |
| 10 | `ann_max` | `pou(ipou)%por(ipor)%ann_max` | `pou_points_of_return` | annual maximim inflow (m3/s) |
| 11 | `frac` | `pou(ipou)%por(ipor)%frac` | `pou_points_of_return` | fraction of POU outflow to each POR (m3/s) |

As in the POD record, positions 2 and 5 both write `pou(ipou)%por(ipor)%num`; the later value replaces the earlier one. In a POR record, `pp` is again a local record tag. The reader does not check its value here.

See also [point_of_diver.wro](point_of_diver.wro.md). The old [water_allocation.wro](water_allocation.wro/README.md) page is historical and does not define this layout.
