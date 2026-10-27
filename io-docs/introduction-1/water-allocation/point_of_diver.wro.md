# point_of_diver.wro

This file defines points of diversion (PODs) and their associated places of use (POUs). The default filename is `point_of_diver.wro`, selected through `in_wallo%pod`.

The reader consumes a title line, an integer number of PODs, and a header line. Each POD occupies a record with five fixed values followed by a repeated group of six values for each associated POU. The reader first reads the five fixed values to obtain `ipous`, allocates the POU array, backspaces, and rereads the complete record.

These tables give the exact read order and code identifiers in SWAT+ main `6f515368`. They use internal Fortran names; they do not assert Editor header spellings. Array indices are the reader's loop variables. Declared types identify the owning derived type, or the primitive type of a local variable. Descriptions summarize the source declarations. Units in those comments have not been checked against downstream calculations; recommended defaults and ranges are not supplied by this layout reference.

## POD record and repeated POU group

| Position | Field | Code reference | Declared type | Description |
| --- | --- | --- | --- | --- |
| 1 | `num` | `pod(ipod)%num` | `point_of_diversion` | POD number |
| 2 | `name` | `pod(ipod)%name` | `point_of_diversion` | name of POD |
| 3 | `typ` | `pod(ipod)%typ` | `point_of_diversion` | type of POD |
| 4 | `typ_num` | `pod(ipod)%typ_num` | `point_of_diversion` | POD type number |
| 5 | `pous` | `pod(ipod)%pous` | `point_of_diversion` | number of places of use (POUs) for the POD |
| 6 | `num` | `pod(ipod)%pou(ipou)%num` | `pod_place_of_use` | POU number |
| 7 | `name` | `pod(ipod)%pou(ipou)%name` | `pod_place_of_use` | name of POU |
| 8 | `pod_num` | `pod(ipod)%pou(ipou)%pod_num` | `pod_place_of_use` | POD number in POU |
| 9 | `typ` | `pod(ipod)%pou(ipou)%typ` | `pod_place_of_use` | type of POD |
| 10 | `typ_num` | `pod(ipod)%pou(ipou)%typ_num` | `pod_place_of_use` | POD type number |
| 11 | `right` | `pod(ipod)%pou(ipou)%right` | `pod_place_of_use` | water right |

Positions 1–5 occur once per POD. Positions 6–11 repeat `pod(ipod)%pous` times, with the POU loop index `ipou`. The preliminary read stores that count in the local variable `ipous`; the complete read stores it in `pod(ipod)%pous`.

See also [place_of_use.wro](place_of_use.wro.md). These pages describe the current reader; they do not establish that every water-allocation option has been validated in a model run.
