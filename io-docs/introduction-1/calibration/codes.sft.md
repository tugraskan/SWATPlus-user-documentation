# codes.sft

| Field       | Description                            | Type   |
| ----------- | -------------------------------------- | ------ |
| hyd\_hru    | HRU water balance soft calibration     | string |
| hyd\_hrulte\* | HRU-lte water balance soft calibration | string |
| plt         | Plant growth soft calibration          | string |
| sed         | Land phase sediment soft calibration   | string |
| nut | Land phase nutrient soft-calibration flag (calibration routine not implemented) | string |
| chsed       | Channel sediment soft calibration      | string |
| chnut | Channel nutrient soft-calibration flag (calibration routine not implemented) | string |
| res | Reservoir soft-calibration flag (calibration routine not implemented) | string |

\* Input-file labels marked with an asterisk have different Fortran names: `hyd_hrulte` → `cal_codes%hyd_hrul`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/calsoft_read_codes.f90#L34).
