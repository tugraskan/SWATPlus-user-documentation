---
description: This file controls which output files will be printed during the simulation.
---

# print.prt

The **print.prt** file is formatted differently than most other SWAT+ input files (see figure below). In line three, there are several variables for controlling the time period to be printed. Line five is read but ignored on SWAT+ dev: average-annual output always covers the whole printed period (see [aa\_int\_cnt](aa_int_cnt.md)). In line seven, the user can select to have output files printed in a specific file format (in addition to the default \*.txt output files). In line nine, the user can control the printing of outputs for soils and management as well as flow duration curves. In lines 11 to 90, there is a list of outputs for different spatial levels and objects that can be printed at daily, monthly, yearly, and average annual time steps. This file is read by [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L24-L40). A description of the output files is provided in the [SWAT+ Output Files](https://app.gitbook.com/s/-MTFpIHUB1K63DLhLJaf/swat+-output-files) section.

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption><p>Format of the print.prt file</p></figcaption></figure>

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nyskip](nyskip.md) | Number of years at the beginning of the simulation to not print output | integer |  |  |  |
| [day\_start](day_start.md) | Julian day to start printing output (for daily printing only) | integer |  |  |  |
| [yrc\_start](yrc_start.md) | Calendar year to start printing output (for daily printing only) | integer |  |  |  |
| [day\_end](day_end.md) | Julian day to stop printing output (for daily printing only) | integer |  |  |  |
| [yrc\_end](yrc_end.md) | Calendar year to stop printing output (for daily printing only) | integer |  |  |  |
| [interval](interval.md) | Print interval within the period | integer |  |  |  |
| [aa\_int\_cnt](aa_int_cnt.md) | Number of average-annual print intervals; read but ignored on dev | integer |  |  |  |
| [aa\_yrs](aa_yrs.md) | End years of the average-annual print intervals; not read on dev | integer list |  |  |  |
| [csvout](csvout.md) | Code for printing output in CSV format (y=yes, n=no) | string |  |  |  |
| [use\_obj\_lbls](use_obj_lbls.md) | Code controlling how object rows are read: n = fixed order; any other value = use the object label in the first column | string |  |  |  |
| [cdfout](cdfout.md) | Code for printing output in Net-CDF format (y=yes, n=no) | string |  |  |  |
| [crop\_yld](crop_yld.md) | Code for printing crop-yield output (a=average annual, y=yearly, b=both, n=no) | string |  |  |  |
| [mgtout](mgtout.md) | Code for printing management output (y=yes, n=no) | string |  |  |  |
| [hydcon](hydcon.md) | Code for printing hydrograph connection output (y=yes, n=no) | string |  |  |  |
| [fdcout](fdcout.md) | Code for printing flow duration curve output (y=yes, n=no) | string |  |  |  |
| [object](object.md) | Objects that output can be printed for at different time steps | string |  |  |  |
| [daily](daily.md) | Code for printing daily output (y=yes, n=no) | string |  |  |  |
| [monthly](monthly.md) | Code for printing monthly output (y=yes, n=no) | string |  |  |  |
| [yearly](yearly.md) | Code for printing yearly output (y=yes, n=no) | string |  |  |  |
| [avann](avann.md) | Code for printing average annual output (y=yes, n=no) | string |  |  |  |
