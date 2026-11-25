# Management Practices

There are six SWAT+ input files that define pre-defined management operation parameters, selected from the `ops` line of `file.cio` (`in_ops`, [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L199)) and loaded during database initialization in [`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L26-L31):

* Harvest: [**harv.ops**](harv.ops/README.md)
* Grazing: [**graze.ops**](graze.ops/README.md)
* Irrigation: [**irr.ops**](irr.ops/README.md)
* Application of fertilizers, manure, and pesticides: [**chem\_app.ops**](chem_app.ops/README.md)
* Burning/fire operations: [**fire.ops**](fire.ops/README.md)
* Street sweeping in urban areas: [**sweep.ops**](sweep.ops/README.md)
