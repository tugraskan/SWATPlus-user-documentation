# Object Outputs

`object.prt` requests a hydrograph for a selected model object and gives the output filename. Each request identifies the object type and number and the hydrologic-output type to write. The model creates the requested file and writes the selected object's hydrograph for the simulation.

Because the filename, object identity, and hydrograph type come from `object.prt`, there is no single fixed object-output filename or universal field table. Interpret each generated file with its `object.prt` row and its printed header. A missing or `null` `object.prt` produces no configured object-output files.

This feature is different from the basin, HRU, channel, reservoir, and other standard families selected in `print.prt`.
