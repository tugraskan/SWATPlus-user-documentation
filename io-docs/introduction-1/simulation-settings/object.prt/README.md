---
description: >-
  This file allows the user to print selected output for individual spatial
  objects.
---

# object.prt

The **object.prt** file is commonly used to:

* Print daily channel outflow to compare to observed streamflow a stream gage
* Print daily flow to a file that can be read in as a point source from another SWAT+ simulation

The only timestep output can be printed at using this file is daily. A description of the output files is provided in the [SWAT+ Output Files](https://app.gitbook.com/s/-MTFpIHUB1K63DLhLJaf/swat+-output-files) section.

| Field                         | Description                              | Type    |
| ----------------------------- | ---------------------------------------- | ------- |
| id\* | ID of the object print record            | integer |
| [obj\_typ](obj_typ.md)\* | Type of object to print output for       | string  |
| [obj\_typ\_no](obj_typ_no.md)\* | Number of the object to print output for | integer |
| [hyd\_typ](hyd_typ.md)\* | Type of hydrograph to print              | string  |
| filename                      | User-defined name of output file         | string  |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `obj_typ` → `ob_out(ii)%obtyp`; `obj_typ_no` → `ob_out(ii)%obtypno`; `hyd_typ` → `ob_out(ii)%hydtyp`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/object_read_output.f90#L52).
