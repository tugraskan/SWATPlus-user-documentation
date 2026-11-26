---
description: >-
  This file allows the user to print selected output for individual spatial
  objects.
---

# object.prt

The **object.prt** file is commonly used to:

* Print daily channel outflow to compare to observed streamflow at a stream gage
* Print daily flow to a file that can be read in as a point source from another SWAT+ simulation

This file is read by [`object_read_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/object_read_output.f90#L52-L53) and written daily by [`obj_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/obj_output.f90#L29-L206). Unlike `print.prt` outputs, `object.prt` outputs are written on every simulated day regardless of `nyskip` or `pco%day_print` because `obj_output` is called in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L438-L441) before the `nyskip` check. A description of the output files is provided in the [SWAT+ Output Files](https://app.gitbook.com/s/-MTFpIHUB1K63DLhLJaf/swat+-output-files) section.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id.md) | ID of the object print record | integer |  |  |  |
| [obj\_typ](obj_typ.md) | Type of object to print output for | string |  |  |  |
| [obj\_typ\_no](obj_typ_no.md) | Number of the object to print output for | integer |  |  |  |
| [hyd\_typ](hyd_typ.md) | Type of hydrograph to print | string |  |  |  |
| [filename](filename.md) | User-defined name of output file | string |  |  |  |
