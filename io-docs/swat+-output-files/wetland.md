# Wetland

Wetland output is available at daily, monthly, yearly, and average-annual intervals as `wetland_day`, `wetland_mon`, `wetland_yr`, and `wetland_aa`, with `.txt` and `.csv` variants.

The wetland files share the printed schema used by reservoir output: the identifying columns `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`; the state columns `area`, `precip`, `evap`, `seep`, and `flo_stor`; then stored, incoming, and outgoing constituent blocks.

| Field | Description | Unit |
| --- | --- | --- |
| area | Wetland surface area | ha |
| precip, evap, seep | Precipitation, evaporation, and seepage volumes | ha-m |
| flo_stor | Water stored in the wetland | m3 |
| `sed_stor`, `san_stor`, `sil_stor`, `cla_stor`, `sag_stor`, `lag_stor`, `grv_stor` | Stored sediment and particle-size classes | tons |
| `orgn_stor`, `sedp_stor`, `no3_stor`, `solp_stor`, `chla_stor`, `nh3_stor`, `no2_stor`, `cbod_stor`, `dox_stor` | Stored nutrients and water-quality constituents | kg |
| `flo_in`, `flo_out` | Incoming and outgoing water | m3 |
| `sed_in`, `san_in`, `sil_in`, `cla_in`, `sag_in`, `lag_in`, `grv_in`; `sed_out`, `san_out`, `sil_out`, `cla_out`, `sag_out`, `lag_out`, `grv_out` | Incoming and outgoing sediment and particle-size classes | tons |
| `orgn_in`, `sedp_in`, `no3_in`, `solp_in`, `chla_in`, `nh3_in`, `no2_in`, `cbod_in`, `dox_in`; `orgn_out`, `sedp_out`, `no3_out`, `solp_out`, `chla_out`, `nh3_out`, `no2_out`, `cbod_out`, `dox_out` | Incoming and outgoing nutrients and water-quality constituents | kg |
| null | Printed separator after each storage, inflow, and outflow block | n/a |

Wetland salt and conservative-constituent files have separate schemas; see [Salt Outputs](salt-outputs.md) and [Conservative Constituents](conservative-constituents.md).
