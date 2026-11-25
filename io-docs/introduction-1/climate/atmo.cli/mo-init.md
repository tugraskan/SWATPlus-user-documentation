# mo_init

First calendar month in a monthly series, from 1 to 12. Enter zero for annual layouts. When the simulation starts within a series that begins after January, the initialization can select the wrong row because its index omits the initial month offset.

See [cli_read_atmodep.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep.f90#L40-L66).
