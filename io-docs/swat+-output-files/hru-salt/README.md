# HRU Salt

This page describes SWAT+ main `6f515368525e7d84089ae0f9d33f4c9115de5679`. Enable `hru_salt` in `print.prt`, which selects `pco%salt_hru%d/m/y/a`; salts must also be configured. Files are `hru_salt_day`, `hru_salt_mon`, `hru_salt_yr`, and `hru_salt_aa`, with `.txt` and optional `.csv` variants. CSV also requires `pco%csvout`.

## Salt configuration used by this report

- The [constituents.cs](../../introduction-1/constituents/constituents.cs.md) reader sets the salt count and reads the names in file order. A positive count enables HRU salt chemistry. The chemistry reads fixed positions 1–8 as sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, and bicarbonate. A smaller count can therefore index beyond the array, and changing the order changes which values the chemistry interprets as each ion. The writer's variable-width loop accounts for the values emitted by the code. The chemistry still assumes those eight ordered positions. [Constituent list](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L54-L59), [Chemistry gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L248-L251), [Fixed ion positions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L155-L164)
- The soil–plant record selects a named [salt_hru.ini](../../introduction-1/initialization/salt_hru.ini/) record. The initializer applies the same starting ion concentrations to each layer and converts them to kg/ha using each layer's water storage. The next five soil entries initialize mineral fractions. The plant row is read but its assignment to plant state is commented out. [Record lookup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L114-L120), [Initialization reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_read.f90#L46-L73), [State assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L44-L67)
- The HRU initializer indexes `salt_irrigation` with that same soil record position. The separate irrigation reader loads names but the initializer does not match those names. For salt-enabled HRUs, the irrigation array must exist and contain the positions referenced by the soil records. [Irrigation reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_irr_read.f90#L18-L54), [Positional assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L44-L61)

TXT has explanatory preamble lines before the header. **CSV also has a preamble:** basin/program identification, then `conc = mg/L; other = kg/ha`, then the comma-separated header. It does not begin with the header. The generic CSV unit line also does not describe every average-annual quantity accurately ([file openers and preambles](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L185)).

{% hint style="warning" %}
For eight ions, the printed header has 159 entries but every data row has 151 values. The writer omits the eight gwup values: subsequent values shift eight columns left. The printed uptake positions hold concentrations, conc_so4 holds a signed mass-change diagnostic, and the final eight headings have no values. The average-annual state/concentration calculations also lack day-count normalization.
{% endhint %}

## Printed header

This table preserves the exact printed header order. Descriptions and units identify the **actual value at each printed position** for eight ions, rather than silently reusing the nominal heading meaning. For another ion count, see the WRITE-list rule below. Period differences and their limits follow the table.

| Field | Description | Unit |
| --- | --- | --- |
| [`jday`](jday.md) | Day of year | n/a |
| [`mon`](mon.md) | Month | n/a |
| [`day`](day.md) | Day of month | n/a |
| [`yr`](yr.md) | Calendar year | n/a |
| [`unit`](unit.md) | HRU identifier | n/a |
| [`gis_id`](gis_id.md) | GIS identifier | n/a |
| [`soil_so4`](soil_so4.md) | Sulfate dissolved-ion mass in the soil profile | kg/ha |
| [`soil_ca`](soil_ca.md) | Calcium dissolved-ion mass in the soil profile | kg/ha |
| [`soil_mg`](soil_mg.md) | Magnesium dissolved-ion mass in the soil profile | kg/ha |
| [`soil_na`](soil_na.md) | Sodium dissolved-ion mass in the soil profile | kg/ha |
| [`soil_k`](soil_k.md) | Potassium dissolved-ion mass in the soil profile | kg/ha |
| [`soil_cl`](soil_cl.md) | Chloride dissolved-ion mass in the soil profile | kg/ha |
| [`soil_co3`](soil_co3.md) | Carbonate dissolved-ion mass in the soil profile | kg/ha |
| [`soil_hco3`](soil_hco3.md) | Bicarbonate dissolved-ion mass in the soil profile | kg/ha |
| [`surq_so4`](surq_so4.md) | Sulfate surface-runoff salt diagnostic | kg/ha |
| [`surq_ca`](surq_ca.md) | Calcium surface-runoff salt diagnostic | kg/ha |
| [`surq_mg`](surq_mg.md) | Magnesium surface-runoff salt diagnostic | kg/ha |
| [`surq_na`](surq_na.md) | Sodium surface-runoff salt diagnostic | kg/ha |
| [`surq_k`](surq_k.md) | Potassium surface-runoff salt diagnostic | kg/ha |
| [`surq_cl`](surq_cl.md) | Chloride surface-runoff salt diagnostic | kg/ha |
| [`surq_co3`](surq_co3.md) | Carbonate surface-runoff salt diagnostic | kg/ha |
| [`surq_hco3`](surq_hco3.md) | Bicarbonate surface-runoff salt diagnostic | kg/ha |
| [`latq_so4`](latq_so4.md) | Sulfate lateral-flow salt diagnostic | kg/ha |
| [`latq_ca`](latq_ca.md) | Calcium lateral-flow salt diagnostic | kg/ha |
| [`latq_mg`](latq_mg.md) | Magnesium lateral-flow salt diagnostic | kg/ha |
| [`latq_na`](latq_na.md) | Sodium lateral-flow salt diagnostic | kg/ha |
| [`latq_k`](latq_k.md) | Potassium lateral-flow salt diagnostic | kg/ha |
| [`latq_cl`](latq_cl.md) | Chloride lateral-flow salt diagnostic | kg/ha |
| [`latq_co3`](latq_co3.md) | Carbonate lateral-flow salt diagnostic | kg/ha |
| [`latq_hco3`](latq_hco3.md) | Bicarbonate lateral-flow salt diagnostic | kg/ha |
| [`urbq_so4`](urbq_so4.md) | Sulfate urban-runoff salt diagnostic | kg/ha |
| [`urbq_ca`](urbq_ca.md) | Calcium urban-runoff salt diagnostic | kg/ha |
| [`urbq_mg`](urbq_mg.md) | Magnesium urban-runoff salt diagnostic | kg/ha |
| [`urbq_na`](urbq_na.md) | Sodium urban-runoff salt diagnostic | kg/ha |
| [`urbq_k`](urbq_k.md) | Potassium urban-runoff salt diagnostic | kg/ha |
| [`urbq_cl`](urbq_cl.md) | Chloride urban-runoff salt diagnostic | kg/ha |
| [`urbq_co3`](urbq_co3.md) | Carbonate urban-runoff salt diagnostic | kg/ha |
| [`urbq_hco3`](urbq_hco3.md) | Bicarbonate urban-runoff salt diagnostic | kg/ha |
| [`wetq_so4`](wetq_so4.md) | Sulfate wetland-runoff salt diagnostic | kg/ha |
| [`wetq_ca`](wetq_ca.md) | Calcium wetland-runoff salt diagnostic | kg/ha |
| [`wetq_mg`](wetq_mg.md) | Magnesium wetland-runoff salt diagnostic | kg/ha |
| [`wetq_na`](wetq_na.md) | Sodium wetland-runoff salt diagnostic | kg/ha |
| [`wetq_k`](wetq_k.md) | Potassium wetland-runoff salt diagnostic | kg/ha |
| [`wetq_cl`](wetq_cl.md) | Chloride wetland-runoff salt diagnostic | kg/ha |
| [`wetq_co3`](wetq_co3.md) | Carbonate wetland-runoff salt diagnostic | kg/ha |
| [`wetq_hco3`](wetq_hco3.md) | Bicarbonate wetland-runoff salt diagnostic | kg/ha |
| [`tile_so4`](tile_so4.md) | Sulfate tile-drainage salt diagnostic | kg/ha |
| [`tile_ca`](tile_ca.md) | Calcium tile-drainage salt diagnostic | kg/ha |
| [`tile_mg`](tile_mg.md) | Magnesium tile-drainage salt diagnostic | kg/ha |
| [`tile_na`](tile_na.md) | Sodium tile-drainage salt diagnostic | kg/ha |
| [`tile_k`](tile_k.md) | Potassium tile-drainage salt diagnostic | kg/ha |
| [`tile_cl`](tile_cl.md) | Chloride tile-drainage salt diagnostic | kg/ha |
| [`tile_co3`](tile_co3.md) | Carbonate tile-drainage salt diagnostic | kg/ha |
| [`tile_hco3`](tile_hco3.md) | Bicarbonate tile-drainage salt diagnostic | kg/ha |
| [`perc_so4`](perc_so4.md) | Sulfate deep-percolation salt diagnostic | kg/ha |
| [`perc_ca`](perc_ca.md) | Calcium deep-percolation salt diagnostic | kg/ha |
| [`perc_mg`](perc_mg.md) | Magnesium deep-percolation salt diagnostic | kg/ha |
| [`perc_na`](perc_na.md) | Sodium deep-percolation salt diagnostic | kg/ha |
| [`perc_k`](perc_k.md) | Potassium deep-percolation salt diagnostic | kg/ha |
| [`perc_cl`](perc_cl.md) | Chloride deep-percolation salt diagnostic | kg/ha |
| [`perc_co3`](perc_co3.md) | Carbonate deep-percolation salt diagnostic | kg/ha |
| [`perc_hco3`](perc_hco3.md) | Bicarbonate deep-percolation salt diagnostic | kg/ha |
| [`gwup_so4`](gwup_so4.md) | Sulfate wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_ca`](gwup_ca.md) | Calcium wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_mg`](gwup_mg.md) | Magnesium wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_na`](gwup_na.md) | Sodium wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_k`](gwup_k.md) | Potassium wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_cl`](gwup_cl.md) | Chloride wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_co3`](gwup_co3.md) | Carbonate wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`gwup_hco3`](gwup_hco3.md) | Bicarbonate wetland-seepage salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_so4`](wtsp_so4.md) | Sulfate surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_ca`](wtsp_ca.md) | Calcium surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_mg`](wtsp_mg.md) | Magnesium surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_na`](wtsp_na.md) | Sodium surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_k`](wtsp_k.md) | Potassium surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_cl`](wtsp_cl.md) | Chloride surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_co3`](wtsp_co3.md) | Carbonate surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`wtsp_hco3`](wtsp_hco3.md) | Bicarbonate surface-water irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_so4`](irsw_so4.md) | Sulfate groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_ca`](irsw_ca.md) | Calcium groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_mg`](irsw_mg.md) | Magnesium groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_na`](irsw_na.md) | Sodium groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_k`](irsw_k.md) | Potassium groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_cl`](irsw_cl.md) | Chloride groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_co3`](irsw_co3.md) | Carbonate groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irsw_hco3`](irsw_hco3.md) | Bicarbonate groundwater irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_so4`](irgw_so4.md) | Sulfate outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_ca`](irgw_ca.md) | Calcium outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_mg`](irgw_mg.md) | Magnesium outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_na`](irgw_na.md) | Sodium outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_k`](irgw_k.md) | Potassium outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_cl`](irgw_cl.md) | Chloride outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_co3`](irgw_co3.md) | Carbonate outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irgw_hco3`](irgw_hco3.md) | Bicarbonate outside-source irrigation salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_so4`](irwo_so4.md) | Sulfate rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_ca`](irwo_ca.md) | Calcium rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_mg`](irwo_mg.md) | Magnesium rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_na`](irwo_na.md) | Sodium rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_k`](irwo_k.md) | Potassium rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_cl`](irwo_cl.md) | Chloride rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_co3`](irwo_co3.md) | Carbonate rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`irwo_hco3`](irwo_hco3.md) | Bicarbonate rainfall salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_so4`](rain_so4.md) | Sulfate dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_ca`](rain_ca.md) | Calcium dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_mg`](rain_mg.md) | Magnesium dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_na`](rain_na.md) | Sodium dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_k`](rain_k.md) | Potassium dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_cl`](rain_cl.md) | Chloride dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_co3`](rain_co3.md) | Carbonate dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`rain_hco3`](rain_hco3.md) | Bicarbonate dry-deposition salt diagnostic (shifted under this heading) | kg/ha |
| [`dryd_so4`](dryd_so4.md) | Sulfate road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_ca`](dryd_ca.md) | Calcium road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_mg`](dryd_mg.md) | Magnesium road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_na`](dryd_na.md) | Sodium road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_k`](dryd_k.md) | Potassium road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_cl`](dryd_cl.md) | Chloride road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_co3`](dryd_co3.md) | Carbonate road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`dryd_hco3`](dryd_hco3.md) | Bicarbonate road-salt application diagnostic (shifted under this heading) | kg/ha |
| [`road_so4`](road_so4.md) | Sulfate fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_ca`](road_ca.md) | Calcium fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_mg`](road_mg.md) | Magnesium fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_na`](road_na.md) | Sodium fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_k`](road_k.md) | Potassium fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_cl`](road_cl.md) | Chloride fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_co3`](road_co3.md) | Carbonate fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`road_hco3`](road_hco3.md) | Bicarbonate fertilizer salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_so4`](fert_so4.md) | Sulfate soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_ca`](fert_ca.md) | Calcium soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_mg`](fert_mg.md) | Magnesium soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_na`](fert_na.md) | Sodium soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_k`](fert_k.md) | Potassium soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_cl`](fert_cl.md) | Chloride soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_co3`](fert_co3.md) | Carbonate soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`fert_hco3`](fert_hco3.md) | Bicarbonate soil-amendment salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_so4`](amnd_so4.md) | Sulfate plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_ca`](amnd_ca.md) | Calcium plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_mg`](amnd_mg.md) | Magnesium plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_na`](amnd_na.md) | Sodium plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_k`](amnd_k.md) | Potassium plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_cl`](amnd_cl.md) | Chloride plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_co3`](amnd_co3.md) | Carbonate plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`amnd_hco3`](amnd_hco3.md) | Bicarbonate plant-uptake salt diagnostic (shifted under this heading) | kg/ha |
| [`uptk_so4`](uptk_so4.md) | Sulfate unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_ca`](uptk_ca.md) | Calcium unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_mg`](uptk_mg.md) | Magnesium unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_na`](uptk_na.md) | Sodium unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_k`](uptk_k.md) | Potassium unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_cl`](uptk_cl.md) | Chloride unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_co3`](uptk_co3.md) | Carbonate unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`uptk_hco3`](uptk_hco3.md) | Bicarbonate unweighted mean of soil-layer ion concentrations (shifted under this heading) | g/m3 |
| [`conc_so4`](conc_so4.md) | net dissolved-ion mass change across soil chemistry (shifted under this heading) | kg/ha |
| [`conc_ca`](conc_ca.md) | No corresponding data value | n/a |
| [`conc_mg`](conc_mg.md) | No corresponding data value | n/a |
| [`conc_na`](conc_na.md) | No corresponding data value | n/a |
| [`conc_k`](conc_k.md) | No corresponding data value | n/a |
| [`conc_cl`](conc_cl.md) | No corresponding data value | n/a |
| [`conc_co3`](conc_co3.md) | No corresponding data value | n/a |
| [`conc_hco3`](conc_hco3.md) | No corresponding data value | n/a |
| [`dssl_total`](dssl_total.md) | No corresponding data value | n/a |

## Actual data layout

All eight TXT/CSV interval writers use six prefix values: `time%day, time%mo, time%day_mo, time%yrc, j, ob(iob)%gis_id`, where `j = ihru` and `iob = sp_ob1%hru + j - 1`. They then write the following 18 groups in order, with one value per ion, followed by `hsaltb_*(j)%salt(1)%diss`:

`soil, surq, latq, urbq, wetq, tile, perc, wtsp, irsw, irgw, irwo, rain, dryd, road, fert, amnd, uptk, conc`.

The header instead includes `gwup` between `perc` and `wtsp`. With eight ions, the actual mapping is:

| Printed heading group | Actual value group at those positions | Positions |
| --- | --- | --- |
| soil through perc | Same-named groups | 7–62 |
| gwup | wtsp | 63–70 |
| wtsp | irsw | 71–78 |
| irsw | irgw | 79–86 |
| irgw | irwo | 87–94 |
| irwo | rain | 95–102 |
| rain | dryd | 103–110 |
| dryd | road | 111–118 |
| road | fert | 119–126 |
| fert | amnd | 127–134 |
| amnd | uptk | 135–142 |
| uptk | conc | 143–150 |
| conc_so4 | salt(1)%diss, all-ion net dissolved-mass change | 151 |
| conc_ca through conc_hco3, then dssl_total | No corresponding values | 152–159 |

For `N = cs_db%num_salts`, the data-list width is **6 + 18N + 1**; the literal header remains 159 entries. The eight-ion mappings assume the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate ([fixed header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L111); [daily TXT/CSV](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L123), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L220), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L310)). A header or preamble is not proof that a same-named diagnostic was written.

## State and chemistry diagnostics

The daily `soil` component sums dissolved-ion masses in `cs_soil%ly%salt` over the profile; it does not include the separate solid-mineral `salt_min` pool. The daily `conc` component is the arithmetic mean of `saltc` across soil layers, without weighting by layer water volume or thickness. Its mg/L declaration is numerically equivalent to g/m3 ([producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L798); [dissolved mass and separate mineral pools](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L313)).

The terminal data scalar `diss` is `mass_after - mass_before` across the soil chemistry routine, summed over ions and layers and converted to kg/ha. Positive means a net dissolved-ion gain; negative means a net loss. It is not a gross positive-only mineral-dissolution total, and storage in `salt(1)` does not make it sulfate-only. It appears under `conc_so4`, not under `dssl_total` ([signed diagnostic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L366)).

## Runoff, drainage, and groundwater transfer

The [daily initializer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sim_initday.f90#L82) clears the eight transport arrays. The [HRU controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L787) copies their values into the daily salt record after the transport and lag calculations. The table uses **actual data components**; the `wtsp` component appears under the printed `gwup` headings.

| Component | Calculation and interpretation |
| --- | --- |
| `surq` | [Top-layer runoff loss](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L124) is runoff depth times `cosurfsalt`, capped by available dissolved mass. [Surface storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/stor_surfstor.f90#L137) adds that loss to the previous remainder, releases the fraction `brt(j)`, and keeps the rest. The row contains the released mass per HRU area, which can include older runoff. |
| `latq` | [Lateral soil export](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L142) sums layer losses. The top layer uses `cosurfsalt` and deeper layers use `cosalt`, each times lateral flow depth and capped by remaining dissolved mass. |
| `urbq` | [Urban lag storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/stor_surfstor.f90#L148) releases `surf_bs(28:35,j) * brt(j)`; that buffer is [initialized to zero](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/allocate_parms.f90#L188), and its only identified input is the same `urbqsalt` diagnostic cleared daily. No fresh urban-salt loading producer was identified. Zero values do not establish absence of urban salt export. |
| `wetq` | [Wetland outflow mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt.f90#L42) uses outflow volume times the salt concentration at entry to the salt routine, capped by available mass. It converts kg to kg/ha using HRU area, and [wetland lag storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/stor_surfstor.f90#L157) then releases a fraction of the buffered amount. The separate wetland balance stores outflow before this lag. |
| `tile` | [Drain-layer loss](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L133) uses `cosalt * qtile` only at the configured drain layer, capped by remaining dissolved salt. It is a tile drainage loss, separate from lateral soil flow and bottom percolation. |
| `perc` | [Percolation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L153) passes salt down from each layer to the next and reports only export past the bottom layer. The optional GWFlow handoff copies that same mass per area; this is not measured same-day arrival in the aquifer. |
| `wtsp` | [Wetland seepage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt.f90#L62) takes salt with seepage water, capped by wetland mass remaining after outflow. It divides kg by HRU area and adds the result to the top soil layer. This is a soil input, before any subsequent transport, and is not runoff lag release. |
| `gwup` (omitted) | The intended [upward-transfer calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L76) adds GWFlow `hru_soil` kg/ha contributions by layer. Its local `gw_soil_flag` starts at zero and is never enabled in the routine, so this branch stays off even if global GWFlow soil exchange is enabled. In addition, the HRU-salt writer omits the component entirely. |

The soil routine calculates `cosalt` as mobile ion mass per unit water depth, then applies the surface coefficient to get `cosurfsalt` ([mobile salt calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L108)). It removes salt in the order surface runoff, tile drainage, lateral flow, then percolation, capping each amount by the mass still in the layer. The reported units are kg/ha; downstream [hydrograph construction](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L41) multiplies runoff, lateral, tile, and bottom-export values by HRU area to obtain kg. The combined surface hydrograph adds `surq`, `urbq`, and `wetq`; none of the three alone is the combined surface load.

The GWFlow [soil exchange routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_soil.f90#L100) separately converts transported solute from grams to kg/ha for `hru_soil`. This does not enable the local guard in the HRU salt routine or repair the absent report column.

## Irrigation, deposition, applications, and uptake

The actual data components below follow the shifted positions in the [data layout](#actual-data-layout).

| Actual component | Calculation and source behavior |
| --- | --- |
| `irsw`, `irwo` | The legacy soil delivery routines convert water volume and ion concentration to kg, then divide by HRU area. Their only allocation call in this revision is commented out. The fields retain their initialized or reset values along the traced execution path. [Legacy source branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_irrig.f90#L63) · [Commented call](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_pou_deliv.f90#L60) |
| `irgw` | Both groundwater routines are dormant. The legacy aquifer routine converts its withdrawal to mass per HRU area. The GWFlow routine has soil and wetland branches and would divide the soil delivery by HRU area after the first two solute slots. The pinned source has no active calls to either routine. [Legacy aquifer branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_irrig.f90#L90) · [GWFlow salt delivery](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pump_allo.f90#L118) · [Current withdrawal branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L126) |
| `rain` | Wet deposition adds `0.01 × concentration × precipitation` to the top soil layer. Concentration is in mg/L and precipitation is in mm. The selected deposition timestep determines the concentration series. [Wet deposition calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_rain.f90#L30) |
| `dryd` | The routine adds dry deposition to the same soil layer. It divides monthly values by calendar month length and yearly or average-annual values by 365, including in leap years. Both deposition components require the salt deposition flag. [Dry deposition calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_rain.f90#L42) · [Deposition guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L565) |
| `road` | Monthly and average-annual loadings divide by month length and 365, respectively. The yearly reader weights the annual loading by precipitation on days with positive precipitation and mean temperature below 0 °C. The daily mass enters the top soil layer. The reader allocates the array only if `salt_road` exists, and the application routine accesses the array without checking allocation. [Reader and allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_roadsalt_read.f90#L36) · [Soil application](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_roadsalt.f90#L34) |
| `fert`, `amnd` | Scheduled and decision-table manure operations call the soil routine. It splits application across two layers and uses the lowercase `a` name prefix to select `amnd`. The reader labels its ion values kg/ha, while the calculation multiplies them by a kg/ha application rate. A dimensionless ion fraction is needed for that product to yield kg/ha. The application routine assumes an allocated table. The scheduled standing-water fertilizer branch records a separate wetland input in kg. [Reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert_read.f90#L21) · [Soil calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert.f90#L29) · [Scheduled branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L375) · [Decision-table manure](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L399) · [Wetland calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert_wet.f90#L29) |
| `uptk` | The routine distributes the first plant’s specified daily ion uptake across rooted soil layers, caps each share by the available dissolved mass, and records the amount removed. The growth loop may call it for several plants while the calculation continues to use plant slot 1. [Uptake calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_uptake.f90#L38) · [Call guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_biomass_gro.f90#L91) · [Plant loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_grow.f90#L27) |

## Reporting periods and limits

The HRU writer transfers monthly accumulators only at calendar month end. Yearly and average-annual fluxes, state numerators, and the `diss` scalar omit a final partial month. The day and year divisors do not change to match the omitted values. [Monthly and yearly transfers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L93-L119), [yearly and average-annual scaling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191-L309).

Monthly and yearly **flux diagnostics** sum daily values. Their average-annual members divide accumulated yearly values by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. That divisor is not a count of years actually contributing output.

Monthly **soil mass and concentration** divide daily-state sums by the full calendar-month length, `ndays(time%mo + 1) - ndays(time%mo)`. Yearly states receive those sums before monthly averaging and divide by `time%day_end_yr`. Neither divisor counts actual samples in a partial reporting period.

**Average-annual soil mass and concentration are not mean states.** Their accumulators receive yearly sums before yearly day-count division, then divide only by `time%nbyr`. A steady daily state can therefore be multiplied by roughly the number of days per year. The printed state/concentration units do not repair this missing normalization. The TXT preamble's kg/ha/yr label for soil mass should not be interpreted as a validated stock unit.

The `diss` scalar sums daily/monthly/yearly contributions but is not divided by `time%nbyr` at the end. Its average-annual row is cumulative kg/ha for years reaching that accumulator.

[Daily accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L23), [month-to-year transfer before averaging](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95), [year-to-AA transfer before averaging](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191), and [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288) establish those operations. Month/year arrays reset after their period boundaries independently of the corresponding print flag. The [caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441) places these outputs after the skipped-year gate; configured-year divisors still require care. The input and uptake calculations run during HRU processing. The command routine calls the daily salt diagnostic reset inside the reporting-year gate. When fertilizer, amendment, or uptake additions occur during skipped years, their accumulators can carry those contributions into the first reported day. [Reporting gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441) · [Salt balance call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L650) · [Daily diagnostic reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L415)
