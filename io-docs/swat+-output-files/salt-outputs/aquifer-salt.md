# Aquifer salt fluxes and state variables

Aquifer salt output is written for each aquifer at daily, monthly, yearly, and average annual time steps. A period is active when the model has aquifers (`sp_ob%aqu > 0`), `cs_db%num_salts > 0`, and the `print.prt` flag `pco%salt_aqu%d`, `%m`, `%y`, or `%a` is `y`. [Daily file setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L345-L368), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L375-L376), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L405-L406), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L435-L436), [data writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L35-L187)

* aquifer\_salt\_day.txt
* aquifer\_salt\_day.csv
* aquifer\_salt\_mon.txt
* aquifer\_salt\_mon.csv
* aquifer\_salt\_yr.txt
* aquifer\_salt\_yr.csv
* aquifer\_salt\_aa.txt
* aquifer\_salt\_aa.csv

A `.csv` copy is written only when `pco%csvout == "y"`. [CSV condition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L365-L368)

* Each file starts with the basin name and `prog`, a title line, a definitions list, and one column-name row. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L348-L364)
* Every data row begins with six values: `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Then it holds seven groups of values in the order `gw`, `rchg`, `seep`, `irr`, `div`, `mass`, `conc`. Each group lists all `cs_db%num_salts` salts before the next group starts. The row ends with one `dssl_total` value. [Data row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L36-L44)
* The column-name row is the fixed header record `salt_hdr_aqu`. It names eight salt columns in each group, in the order `so4`, `ca`, `mg`, `na`, `k`, `cl`, `co3`, `hco3`, for example `gw_so4` to `gw_hco3`. [Header record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L36-L100)
* The `dssl` value in each row is the first salt's `diss`, `salt(1)%diss`; the header names it `dssl_total` and the legend names it `dssl`. [Data](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L44), [Header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L99)
* In the CSV files the heading line reads `conc = mg/L; other = kg`, while the `.txt` legend gives `conc` in g/m3. [Daily CSV heading](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L368)

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
| [jday](aquifer-salt/jday.md) | Julian day | integer | n/a |
| [mon](aquifer-salt/mon.md) | Month | integer | n/a |
| [day](aquifer-salt/day.md) | Day of the month | integer | n/a |
| [yr](aquifer-salt/yr.md) | Calendar year | integer | n/a |
| [unit](aquifer-salt/unit.md) | Aquifer number | integer | n/a |
| [gis\_id](aquifer-salt/gis_id.md) | GIS ID of the aquifer | integer | n/a |
| [gw\_so4 to gw\_hco3](aquifer-salt/gw.md) | Salt mass in groundwater discharge (aquifer --> stream) | real | kg |
| [rchg\_so4 to rchg\_hco3](aquifer-salt/rchg.md) | Salt mass in groundwater recharge (soil --> aquifer) | real | kg |
| [seep\_so4 to seep\_hco3](aquifer-salt/seep.md) | Salt mass in groundwater seepage (aquifer --> deep) | real | kg |
| [irr\_so4 to irr\_hco3](aquifer-salt/irr.md) | Salt mass in groundwater irrigation (aquifer --> soil) | real | kg |
| [div\_so4 to div\_hco3](aquifer-salt/div.md) | Salt mass removed (-) or added (+) via diversion | real | kg |
| [mass\_so4 to mass\_hco3](aquifer-salt/mass.md) | Salt mass stored in aquifer | real | kg |
| [conc\_so4 to conc\_hco3](aquifer-salt/conc.md) | Salt concentration in groundwater | real | g/m3 |
| [dssl\_total](aquifer-salt/dssl.md) | Salt mass dissolved from aquifer minerals (mineral --> aquifer) | real | kg |

## Reporting differences

* The file title ends in `daily`, `monthly`, `yearly`, or `average annual`. [Titles](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L350)
* In the monthly and yearly legends, the `mass` and `conc` lines end with `(averaged over month)` or `(averaged over year)`. In the average annual legend they end with `(averaged over years)`. [Monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L390-L391), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L420-L421), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L450-L451)
* In the average annual legend, the `gw`, `rchg`, `seep`, `irr`, `div`, and `dssl` lines give the unit `kg/yr`. `mass` stays `kg` and `conc` stays g/m3. [Average annual legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L445-L452)
* Monthly rows divide `mass` and `conc` by the days in the month. Yearly rows divide them by `time%day_end_yr`. Average annual rows divide the seven category groups by `time%nbyr`; none of those lines divides `diss`. [Monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L72-L76), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L125-L129), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L166-L176)
