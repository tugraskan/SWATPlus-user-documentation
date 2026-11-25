# Subdaily SD Channel Flow

`channel_sd_subday.txt` has its own nine-column data schema:

| Field | Description | Unit |
| --- | --- | --- |
| jday | Day of year | n/a |
| mon | Month | n/a |
| day | Day of month | n/a |
| yr | Calendar year | n/a |
| unit | Channel identifier | n/a |
| gis_id | GIS identifier | n/a |
| tstep | Within-day time-step index | n/a |
| name | Object name | n/a |
| flo_out | Outflow at this subdaily step | m3/s |

The writer supplies `ii` and `ob(iob)%hyd_flo(1,ii)` for the final step index and flow positions ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L23); [header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L603)).

The source has additional header/output inconsistencies: the TXT units object is declared with the 33-field morphology type even though a separate nine-field units type exists. The CSV opener prints the 33-field morphology header; no data-row write for subdaily flow appears in the inspected source. Its unit 4814 is also reused for `sd_chanbud_yr.csv`, which has an annual budget writer. Treat the nine-column schema above as the TXT data layout, rather than assuming the CSV has equivalent populated rows ([declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L616); [subdaily opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L10); [annual-budget opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L248)). The consequences of enabling both files together require runtime validation.


[Back to the Channel index](README.md).