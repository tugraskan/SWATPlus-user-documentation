# Landuse and Management

Several SWAT+ input files control the simulation of land use, plant communities, and management operations:

Selected from the `lum` line of `file.cio` (`in_lum`, [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L202-L209)) and loaded during database initialization in [`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L32), [`#L46-L49`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L46-L49):

* [**landuse.lum**](landuse.lum/README.md) summarizes land use and management pointers for each HRU land-use type;
* [**management.sch**](management.sch/README.md) schedules management operations by date or heat units and/or lists decision tables for conditional management;
* [**cntable.lum**](cntable.lum/README.md) lists typical SCS Curve Number values for different land use types and hydrologic soil groups;
* [**cons\_practice.lum**](cons_practice.lum/README.md) lists USLE P factors and maximum slope lengths for conservation practices;
* [**ovn\_table.lum**](ovn_table.lum/README.md) lists overland Manning's n values for different tillage and land cover types.

Selected from the `init` line of `file.cio` (`in_init%plant`, loaded in [`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L44) via [`readpcom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L29-L36)):

* [**plant.ini**](plant.ini/README.md) stores initial states for plants growing in a rotation or plant community.

Read directly from the simulation working directory (not selected through `file.cio`):

* [**transplant.ops**](transplant.ops/README.md) defines plant states applied during transplanting ([`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L15));
* [**puddle.ops**](puddle.ops/README.md) defines puddling parameters for rice-paddy operations ([`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L33));
* [**manure\_allo.mnu**](manure_allo.mnu/README.md) defines manure sources, receiving objects, and allocation decision tables ([`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L89)).

Conditional management decision tables referenced by `management.sch` and `manure_allo.mnu` are defined in [**lum.dtl**](../decision-tables/lum.dtl/README.md).
