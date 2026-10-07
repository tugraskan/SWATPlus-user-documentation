---
description: >-
  The pesticide database summarizes parameters used by the model to simulate the
  fate and transport of different types of pesticides.
---

# pesticide.pes

| Field                           | Description                                                            |  Type  |      Unit      | Default |      Range      |
| ------------------------------- | ---------------------------------------------------------------------- | :----: | :------------: | :-----: | :-------------: |
| [name](name_pestdb.md)          | Name of the pesticide record                                           | string |       n/a      |   n/a   |       n/a       |
| [soil\_ads](soil_ads.md)        | Soil adsorption coefficient normalized for soil organic carbon content |  real  | (mg/kg)/(mg/L) |   0.0   | 1.0-999999999.0 |
| [frac\_wash](frac_wash.md)      | Fraction of pesticide on foliage that is washed off by rainfall event  |  real  |    fraction    |   0.0   |     0.0-1.0     |
| [hl\_foliage](hl_foliage.md)    | Half-life of the pesticide on the foliage                              |  real  |      days      |   0.0   |   0.0-10000.0   |
| [hl\_soil](hl_soil.md)          | Half-life of the pesticide in the soil                                 |  real  |      days      |   0.0   |   0.0-100000.0  |
| [solub](solub.md)               | Solubility of the pesticide in water                                   |  real  |   mg/L (ppm)   |   0.0   |                 |
| [aq\_hlife](aq_reac.md)         | Half-life of the pesticide in the water                                |  real  |      days      |   0.0   |                 |
| [aq\_volat](aq_volat.md)        | Aquatic volatilization coefficient                                     |  real  |      m/day     |   0.0   |                 |
| [mol\_wt](mol_wt.md)            | Molecular weight to calculate mixing velocity                          |  real  |      g/mol     |   0.0   |                 |
| [aq\_resus](aq_resus.md)        | Aquatic resuspension velocity for pesticide sorbed to sediment         |  real  |      m/day     |   0.0   |                 |
| [aq\_settle](aq_settle.md)      | Aquatic settling velocity for pesticide sorbed to sediment             |  real  |      m/day     |   0.0   |                 |
| [ben\_act\_dep](ben_act_dep.md) | Depth of the active benthic layer                                      |  real  |        m       |   0.0   |                 |
| [ben\_bury](ben_bury.md)        | Burial velocity in the benthic sediment                                |  real  |      m/day     |   0.0   |                 |
| [ben\_hlife](ben_reac.md)       | Half-life of the pesticide in the benthic sediment                     |  real  |      days      |   0.0   |                 |
| pl\_uptake                      | Fraction of the pesticide taken up by the plant                        |  real  |    fraction    |   0.0   |                 |
| harvest\_sink                   | 1 = the plant is a 100% sink (pesticide is lost on uptake); 0 = pesticide accumulates in the plant and returns to the soil at harvest or kill |  real  |       n/a      |   1.0   |      0 or 1     |
| resistance\_n                   | Resistance blending: 0 = use the actual soil water concentration; 1 = use the field-capacity concentration |  real  |      none      |   1.0   |     0.0-1.0     |
| description                     | Description of the pesticide                                           | string |       n/a      |   n/a   |       n/a       |
