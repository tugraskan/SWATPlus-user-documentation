# calibration.cal

| Field     | Description                            | Type    |
| --------- | -------------------------------------- | ------- |
| name      | Name of the parameter to be calibrated | string  |
| chg\_type | Type of change applied                 | string  |
| val       | Change value                           | real    |
| conds     | Conditions                             | integer |
| lyr1      | Layer 1                                | integer |
| lyr2      | Layer 2                                | integer |
| year1     | Year 1                                 | integer |
| year2     | Year 2                                 | integer |
| day1      | Day 1                                  | integer |
| day2      | Day 2                                  | integer |
| obj\_tot | Total number of objects                | integer |

The file starts with a title line, a calibration-record count, and a header line. Each change record names a parameter from cal_parms.cal. When obj_tot is positive, the record continues with an object-selection list. With obj_tot equal to zero, SWAT+ selects the default objects for the parameter's object type. On main at 6f515368, gwf_riv defaults to all SWAT-DEG channels and gwf_sgl selects the single global element. These object types come from cal_parms.cal; they are not additional columns in calibration.cal.

For GWFlow aquifer_delay, calibration changes the delay in days and then recomputes the recharge decay coefficient as exp(-1/(delay_days + 0.000001)). It does not apply the calibration change directly to the coefficient. stream_bed is changed only when the selected element index is 1, preventing repeated changes of the same global value.
