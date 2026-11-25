# Routing-unit salt balance

Configure salts and select the desired periods on `ru_salt` in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). At least one routing unit is required. The files are named `rout_unit_salt_*`. Set `csvout` to `y` for CSV copies. Daily rows use the daily switch after the skipped years without a separate day window or interval. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L700), [Output caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L612), [Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L46)

## Column order

The first six headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. The header has 127 columns. The writer emits one value per configured ion for each of the 15 ion groups, plus one `dssl_total` value, giving 127 row values with eight ions. CSV files have a standalone `all values in kg` note before the headings in every period. [Header declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L357), [CSV preamble](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L729), [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L48)

For full HRU contributions, `total_*` sums surface runoff, lateral flow, and tile flow. The surface-runoff contribution includes urban runoff and wetland outflow. Percolation has its own columns. The TXT preamble includes percolation in its description of the total. The routing-unit report accumulates the salt contributions from full HRU elements. Its area-based diagnostics convert kg/ha to kg using each HRU's area. [HRU runoff contributions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L98), [HRU total](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L180), [Routing-unit accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L150)

| Field | Description | Unit |
| --- | --- | --- |
| [`total_so4`](total_so4.md) | Sulfate in surface runoff, lateral flow, and tile flow | kg |
| [`total_ca`](total_ca.md) | Calcium in surface runoff, lateral flow, and tile flow | kg |
| [`total_mg`](total_mg.md) | Magnesium in surface runoff, lateral flow, and tile flow | kg |
| [`total_na`](total_na.md) | Sodium in surface runoff, lateral flow, and tile flow | kg |
| [`total_k`](total_k.md) | Potassium in surface runoff, lateral flow, and tile flow | kg |
| [`total_cl`](total_cl.md) | Chloride in surface runoff, lateral flow, and tile flow | kg |
| [`total_co3`](total_co3.md) | Carbonate in surface runoff, lateral flow, and tile flow | kg |
| [`total_hco3`](total_hco3.md) | Bicarbonate in surface runoff, lateral flow, and tile flow | kg |
| [`perc_so4`](perc_so4.md) | Sulfate: percolation | kg |
| [`perc_ca`](perc_ca.md) | Calcium: percolation | kg |
| [`perc_mg`](perc_mg.md) | Magnesium: percolation | kg |
| [`perc_na`](perc_na.md) | Sodium: percolation | kg |
| [`perc_k`](perc_k.md) | Potassium: percolation | kg |
| [`perc_cl`](perc_cl.md) | Chloride: percolation | kg |
| [`perc_co3`](perc_co3.md) | Carbonate: percolation | kg |
| [`perc_hco3`](perc_hco3.md) | Bicarbonate: percolation | kg |
| [`surq_so4`](surq_so4.md) | Sulfate: surface runoff | kg |
| [`surq_ca`](surq_ca.md) | Calcium: surface runoff | kg |
| [`surq_mg`](surq_mg.md) | Magnesium: surface runoff | kg |
| [`surq_na`](surq_na.md) | Sodium: surface runoff | kg |
| [`surq_k`](surq_k.md) | Potassium: surface runoff | kg |
| [`surq_cl`](surq_cl.md) | Chloride: surface runoff | kg |
| [`surq_co3`](surq_co3.md) | Carbonate: surface runoff | kg |
| [`surq_hco3`](surq_hco3.md) | Bicarbonate: surface runoff | kg |
| [`latq_so4`](latq_so4.md) | Sulfate: lateral flow | kg |
| [`latq_ca`](latq_ca.md) | Calcium: lateral flow | kg |
| [`latq_mg`](latq_mg.md) | Magnesium: lateral flow | kg |
| [`latq_na`](latq_na.md) | Sodium: lateral flow | kg |
| [`latq_k`](latq_k.md) | Potassium: lateral flow | kg |
| [`latq_cl`](latq_cl.md) | Chloride: lateral flow | kg |
| [`latq_co3`](latq_co3.md) | Carbonate: lateral flow | kg |
| [`latq_hco3`](latq_hco3.md) | Bicarbonate: lateral flow | kg |
| [`tile_so4`](tile_so4.md) | Sulfate: tile flow | kg |
| [`tile_ca`](tile_ca.md) | Calcium: tile flow | kg |
| [`tile_mg`](tile_mg.md) | Magnesium: tile flow | kg |
| [`tile_na`](tile_na.md) | Sodium: tile flow | kg |
| [`tile_k`](tile_k.md) | Potassium: tile flow | kg |
| [`tile_cl`](tile_cl.md) | Chloride: tile flow | kg |
| [`tile_co3`](tile_co3.md) | Carbonate: tile flow | kg |
| [`tile_hco3`](tile_hco3.md) | Bicarbonate: tile flow | kg |
| [`wtsp_so4`](wtsp_so4.md) | Sulfate: wetland seepage | kg |
| [`wtsp_ca`](wtsp_ca.md) | Calcium: wetland seepage | kg |
| [`wtsp_mg`](wtsp_mg.md) | Magnesium: wetland seepage | kg |
| [`wtsp_na`](wtsp_na.md) | Sodium: wetland seepage | kg |
| [`wtsp_k`](wtsp_k.md) | Potassium: wetland seepage | kg |
| [`wtsp_cl`](wtsp_cl.md) | Chloride: wetland seepage | kg |
| [`wtsp_co3`](wtsp_co3.md) | Carbonate: wetland seepage | kg |
| [`wtsp_hco3`](wtsp_hco3.md) | Bicarbonate: wetland seepage | kg |
| [`irsw_so4`](irsw_so4.md) | Sulfate: surface-water irrigation | kg |
| [`irsw_ca`](irsw_ca.md) | Calcium: surface-water irrigation | kg |
| [`irsw_mg`](irsw_mg.md) | Magnesium: surface-water irrigation | kg |
| [`irsw_na`](irsw_na.md) | Sodium: surface-water irrigation | kg |
| [`irsw_k`](irsw_k.md) | Potassium: surface-water irrigation | kg |
| [`irsw_cl`](irsw_cl.md) | Chloride: surface-water irrigation | kg |
| [`irsw_co3`](irsw_co3.md) | Carbonate: surface-water irrigation | kg |
| [`irsw_hco3`](irsw_hco3.md) | Bicarbonate: surface-water irrigation | kg |
| [`irgw_so4`](irgw_so4.md) | Sulfate: groundwater irrigation | kg |
| [`irgw_ca`](irgw_ca.md) | Calcium: groundwater irrigation | kg |
| [`irgw_mg`](irgw_mg.md) | Magnesium: groundwater irrigation | kg |
| [`irgw_na`](irgw_na.md) | Sodium: groundwater irrigation | kg |
| [`irgw_k`](irgw_k.md) | Potassium: groundwater irrigation | kg |
| [`irgw_cl`](irgw_cl.md) | Chloride: groundwater irrigation | kg |
| [`irgw_co3`](irgw_co3.md) | Carbonate: groundwater irrigation | kg |
| [`irgw_hco3`](irgw_hco3.md) | Bicarbonate: groundwater irrigation | kg |
| [`irwo_so4`](irwo_so4.md) | Sulfate: outside-source irrigation | kg |
| [`irwo_ca`](irwo_ca.md) | Calcium: outside-source irrigation | kg |
| [`irwo_mg`](irwo_mg.md) | Magnesium: outside-source irrigation | kg |
| [`irwo_na`](irwo_na.md) | Sodium: outside-source irrigation | kg |
| [`irwo_k`](irwo_k.md) | Potassium: outside-source irrigation | kg |
| [`irwo_cl`](irwo_cl.md) | Chloride: outside-source irrigation | kg |
| [`irwo_co3`](irwo_co3.md) | Carbonate: outside-source irrigation | kg |
| [`irwo_hco3`](irwo_hco3.md) | Bicarbonate: outside-source irrigation | kg |
| [`rain_so4`](rain_so4.md) | Sulfate: rainfall input | kg |
| [`rain_ca`](rain_ca.md) | Calcium: rainfall input | kg |
| [`rain_mg`](rain_mg.md) | Magnesium: rainfall input | kg |
| [`rain_na`](rain_na.md) | Sodium: rainfall input | kg |
| [`rain_k`](rain_k.md) | Potassium: rainfall input | kg |
| [`rain_cl`](rain_cl.md) | Chloride: rainfall input | kg |
| [`rain_co3`](rain_co3.md) | Carbonate: rainfall input | kg |
| [`rain_hco3`](rain_hco3.md) | Bicarbonate: rainfall input | kg |
| [`dryd_so4`](dryd_so4.md) | Sulfate: dry deposition | kg |
| [`dryd_ca`](dryd_ca.md) | Calcium: dry deposition | kg |
| [`dryd_mg`](dryd_mg.md) | Magnesium: dry deposition | kg |
| [`dryd_na`](dryd_na.md) | Sodium: dry deposition | kg |
| [`dryd_k`](dryd_k.md) | Potassium: dry deposition | kg |
| [`dryd_cl`](dryd_cl.md) | Chloride: dry deposition | kg |
| [`dryd_co3`](dryd_co3.md) | Carbonate: dry deposition | kg |
| [`dryd_hco3`](dryd_hco3.md) | Bicarbonate: dry deposition | kg |
| [`road_so4`](road_so4.md) | Sulfate: road-salt application | kg |
| [`road_ca`](road_ca.md) | Calcium: road-salt application | kg |
| [`road_mg`](road_mg.md) | Magnesium: road-salt application | kg |
| [`road_na`](road_na.md) | Sodium: road-salt application | kg |
| [`road_k`](road_k.md) | Potassium: road-salt application | kg |
| [`road_cl`](road_cl.md) | Chloride: road-salt application | kg |
| [`road_co3`](road_co3.md) | Carbonate: road-salt application | kg |
| [`road_hco3`](road_hco3.md) | Bicarbonate: road-salt application | kg |
| [`fert_so4`](fert_so4.md) | Sulfate: fertilizer input | kg |
| [`fert_ca`](fert_ca.md) | Calcium: fertilizer input | kg |
| [`fert_mg`](fert_mg.md) | Magnesium: fertilizer input | kg |
| [`fert_na`](fert_na.md) | Sodium: fertilizer input | kg |
| [`fert_k`](fert_k.md) | Potassium: fertilizer input | kg |
| [`fert_cl`](fert_cl.md) | Chloride: fertilizer input | kg |
| [`fert_co3`](fert_co3.md) | Carbonate: fertilizer input | kg |
| [`fert_hco3`](fert_hco3.md) | Bicarbonate: fertilizer input | kg |
| [`amnd_so4`](amnd_so4.md) | Sulfate: amendment input | kg |
| [`amnd_ca`](amnd_ca.md) | Calcium: amendment input | kg |
| [`amnd_mg`](amnd_mg.md) | Magnesium: amendment input | kg |
| [`amnd_na`](amnd_na.md) | Sodium: amendment input | kg |
| [`amnd_k`](amnd_k.md) | Potassium: amendment input | kg |
| [`amnd_cl`](amnd_cl.md) | Chloride: amendment input | kg |
| [`amnd_co3`](amnd_co3.md) | Carbonate: amendment input | kg |
| [`amnd_hco3`](amnd_hco3.md) | Bicarbonate: amendment input | kg |
| [`uptk_so4`](uptk_so4.md) | Sulfate: plant uptake | kg |
| [`uptk_ca`](uptk_ca.md) | Calcium: plant uptake | kg |
| [`uptk_mg`](uptk_mg.md) | Magnesium: plant uptake | kg |
| [`uptk_na`](uptk_na.md) | Sodium: plant uptake | kg |
| [`uptk_k`](uptk_k.md) | Potassium: plant uptake | kg |
| [`uptk_cl`](uptk_cl.md) | Chloride: plant uptake | kg |
| [`uptk_co3`](uptk_co3.md) | Carbonate: plant uptake | kg |
| [`uptk_hco3`](uptk_hco3.md) | Bicarbonate: plant uptake | kg |
| [`dssl_total`](dssl_total-routing-unit-salt-balance.md) | Running net change in dissolved soil salt from chemistry | kg |

## Daily values

The five routed-load groups copy the full-HRU salt hydrographs in kg. They use the whole HRU's salt load even where the water and sediment hydrographs use element fractions, area expansion factors, or delivery ratios. The other groups use each full HRU's area to convert kg/ha to kg. The three irrigation groups use the corresponding HRU diagnostics, which have no active salt producer on this revision. [Element factors and routed loads](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L108-L159), [Area-based diagnostics](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L160-L185), [HRU salt inputs](../hru-salt/README.md#irrigation-deposition-applications-and-uptake)

The writer clears the daily ion groups after it adds them to the monthly sums. That reset runs only after the skipped reporting years, so the first reporting day can include salt accumulated during those years. The reset leaves `dssl_total` untouched throughout the simulation. The daily column therefore reports a running sum of the signed dissolved-mass changes from HRU soil chemistry. [Reporting-year gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L440-L442), [Routing-unit output call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L612-L619), [Daily accumulation and reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L27-L100), [Soil chemistry diagnostic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L361-L369)

## Reporting periods

The routed-load groups and the HRU-derived terms, including `dssl_total`, transfer monthly values only at calendar month end. Their yearly and average-annual rows omit the contributions from reporting days in a final partial month. [Month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L104-L121), [Year transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L179-L196)

For the ion groups, monthly and yearly rows sum the daily loads. Average-annual rows divide the ion-group totals by the configured number of simulation years (`time%nbyr`), giving kg/yr even though the CSV note says kg. The monthly `dssl_total` adds the daily running sums, the yearly field adds the monthly running sums, and the average-annual field adds the yearly running sums. Monthly and yearly resets also skip this field, so earlier changes can be counted repeatedly at every level. The average-annual field receives no year division despite the TXT label of kg/yr. [Month reset and year transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L159-L196), [Year reset and average-annual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_salt_output.f90#L235-L287), [Average-annual preamble](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L823)

HRU salt output has a different 159-heading schema and is documented on the [HRU Salt](../hru-salt/README.md) page.

[Back to the Salt Outputs index](README.md).
