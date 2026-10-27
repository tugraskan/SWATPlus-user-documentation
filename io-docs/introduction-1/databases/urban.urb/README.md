---
description: >-
  The urban database summarizes parameters used by the model to simulate
  different types of urban areas.
---

# urban.urb

| Field                           | Description                                                                        |  Type  |    Unit    | Default |    Range   |
| ------------------------------- | ---------------------------------------------------------------------------------- | :----: | :--------: | :-----: | :--------: |
| [name](name_urbdb.md) | Name of the urban land type                                                        | string |     n/a    |   n/a   |     n/a    |
| [frac\_imp](frac_imp.md) | Fraction of total impervious area in urban land type                               |  real  |  fraction  |   0.05  |   0.0-1.0  |
| [frac\_dc\_imp](frac_dc_imp.md) | Fraction of directly connected impervious area in urban land type                  |  real  |  fraction  |   0.05  |   0.0-1.0  |
| [curb\_den](curb_den.md) | Curb length density                                                                |  real  |    km/ha   |   0.0   |   0.0-1.0  |
| [urb\_wash](urb_wash.md) | Wash-off coefficient for removal of constituents from impervious surfaces          |  real  |    1/mm    |   0.0   |   0.0-1.0  |
| [dirt\_max](dirt_max.md) | Maximum amount of solids allowed to build up on impervious surfaces                |  real  | kg/curb km |  1000.0 | 0.0-2000.0 |
| [t\_halfmax](t_halfmax.md) | Time for amount of solids on impervious areas to build up to 1/2 of maximum level  |  real  |    days    |   1.0   |  0.0-100.0 |
| [conc\_totn](conc_totn.md) | Concentration of total N in suspended solid load from impervious areas             |  real  |    mg/kg   |   0.0   | 0.0-1000.0 |
| [conc\_totp](conc_totp.md) | Concentration of total P in suspended solid load from impervious areas             |  real  |    mg/kg   |   0.0   | 0.0-1000.0 |
| [conc\_no3n](conc_no3.md) | Concentration of NO3-N in suspended solid load from impervious areas               |  real  |    mg/kg   |   0.0   |  0.0-50.0  |
| [urb\_cn](urb_cn.md) | Not used. Daily curve-number runoff uses a fixed impervious-area curve number of 98. | real | none | 0.0 | 30.0-100.0 |
