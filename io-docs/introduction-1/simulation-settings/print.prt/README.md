---
description: This file controls which output files will be printed during the simulation.
---

# print.prt

The **print.prt** file is formatted differently than most other SWAT+ input files (see figure below). In line three, there are several variables for controlling the time period to be printed. In line five, the user can specify the number of print intervals for average annual output. In line seven, the user can select to have output files printed in a specific file format (in addition to the default \*.txt output files). In line 9, the user can control the printing of outputs for soils and management as well as flow duration curves. In lines 11 to 90, there is a list of outputs for different spatial levels and objects that can be printed at daily, monthly, yearly, and average annual time steps. A description of the output files is provided in the [SWAT+ Output Files](https://app.gitbook.com/s/-MTFpIHUB1K63DLhLJaf/swat+-output-files) section.  &#x20;

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption><p>Format of the print.prt file</p></figcaption></figure>

| Field                         | Description                                                            | Type    |
| ----------------------------- | ---------------------------------------------------------------------- | ------- |
| [nyskip](nyskip.md)           | Number of years at the beginning of the simulation to not print output | integer |
| day\_start                    | Julian day to start printing output (for daily printing only)          | integer |
| yrc\_start                    | Calendar year to start printing output                                 | integer |
| day\_end                      | Julian day to stop printing output (for daily printing only)           | integer |
| yrc\_end                      | Calendar year to stop printing output                                  | integer |
| [interval](interval.md) | Print interval within the period                                       | integer |
| [aa\_int\_cnt](aa_int_cnt.md) | Number of print intervals for average annual output                    | integer |
| aa\_yrs | End years for the average annual print intervals; list exactly aa_int_cnt years on the same line | integer list |
| csvout                        | Code for printing output in CSV format (y=yes, n=no)                   | string  |
| [use\_obj\_lbls](use_obj_lbls.md) | Code controlling how object rows are read: n = fixed order; any other value = use the object label in the first column | string |
| cdfout                        | Code for printing output in Net-CDF format (y=yes, n=no)               | string  |
| crop\_yld | Code for printing crop-yield output (a=average annual, y=yearly, b=both, n=no) | string |
| mgtout                        | Code for printing management output (y=yes, n=no)                      | string  |
| [hydcon](hydcon.md)           | Code for printing hydrograph connection output (y=yes, n=no)           | string  |
| fdcout                        | Code for printing flow duration curve output (y=yes, n=no)             | string  |
| [object](object.md) | Objects that output can be printed for at different time steps         | string  |
| daily | Code for printing daily output (y=yes, n=no)                           | string  |
| monthly | Code for printing monthly output (y=yes, n=no)                         | string  |
| yearly | Code for printing yearly output (y=yes, n=no)                          | string  |
| avann | Code for printing average annual output (y=yes, n=no)                  | string  |
