---
description: This file contains the reservoir and wetland nutrient parameters.
---

# nutrients.res

| Field                                               | Description                                                            |   Type  |  Unit | Default |   Range  |
| --------------------------------------------------- | ---------------------------------------------------------------------- | :-----: | :---: | :-----: | :------: |
| [name](untitled.md)                                 | Name of the reservoir and wetland nutrient record                      |  string |  n/a  |   n/a   |    n/a   |
| [mid\_start](untitled-7.md)\* | Beginning month of the mid-year nutrient settling period               | integer |  n/a  |    5    |   0-12   |
| [mid\_end](untitled-6.md)\* | Ending month of the mid-year nutrient settling period                  | integer |  n/a  |    10   |   0-12   |
| <p><a href="untitled-5.md">mid_n_stl</a></p><p></p>\* | Annual nitrogen loss-rate coefficient used during the mid-year nutrient period | real | 1/year | 5.50 | 1.0-15.0 |
| [n\_stl](untitled-4.md)\* | Annual nitrogen loss-rate coefficient used outside the mid-year nutrient period | real | 1/year | 5.50 | 1.0-15.0 |
| [mid\_p\_stl](untitled-3.md)\* | Annual phosphorus loss-rate coefficient used during the mid-year nutrient period | real | 1/year | 10.0 | 2.0-20.0 |
| [p\_stl](untitled-2.md)\* | Annual phosphorus loss-rate coefficient used outside the mid-year nutrient period | real | 1/year | 10.0 | 2.0-20.0 |
| [chla\_co](untitled-1.md)\* | Annual loss-rate coefficient for soluble inorganic nitrogen (NO3, NH3, and NO2) | real | 1/year | 1.0 | 0.0-1.0 |
| [secchi\_co](secchi_co.md)\* | Annual loss-rate coefficient for soluble phosphorus | real | 1/year | 1.0 | 0.50-2.0 |
| [theta\_n](theta_n.md)                              | Temperature adjustment for nitrogen loss (settling)                    |   real  |  n/a  |   1.0   |          |
| [theta\_p](theta_p.md)                              | Temperature adjustment for phosphorus loss (settling)                  |   real  |  n/a  |   1.0   |          |
| [n\_min\_stl](n_min_stl.md)\* | Minimum nitrogen concentration for settling                            |   real  |  ppm  |   0.10  |          |
| [p\_min\_stl](p_min_stl.md)\* | Minimum phosphorus concentration for settling                          |   real  |  ppm  |   0.01  |          |

\* Input-file labels marked with an asterisk have different Fortran names: `mid_start` → `res_nut(ires)%ires1`; `mid_end` → `res_nut(ires)%ires2`; `mid_n_stl` → `res_nut(ires)%nsetlr1`; `n_stl` → `res_nut(ires)%nsetlr2`; `mid_p_stl` → `res_nut(ires)%psetlr1`; `p_stl` → `res_nut(ires)%psetlr2`; `chla_co` → `res_nut(ires)%nsolr`; `secchi_co` → `res_nut(ires)%psolr`; `n_min_stl` → `res_nut(ires)%conc_nmin`; `p_min_stl` → `res_nut(ires)%conc_pmin`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_nut.f90#L55).
