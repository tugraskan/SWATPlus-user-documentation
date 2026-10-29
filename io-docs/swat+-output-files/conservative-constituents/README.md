# Conservative Constituents

Conservative-constituent output tracks selenate (`seo4`), selenite (`seo3`), and boron (`born`). The files are produced only when these constituents are configured and the corresponding print option is enabled. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`, with TXT and CSV variants.

All object-level files begin with `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. The remaining printed headings differ by object type.

## HRU

{% hint style="warning" %}
In the inspected main version, the HRU data writer omits the three `gwup_` values even though those headings are printed. Values after `perc_born` are shifted under the wrong headings, and the final three printed headings have no corresponding row values.
{% endhint %}

The `hru_cs_*` files contain one three-constituent group for each process.

| Field | Description | Unit |
| --- | --- | --- |
| [`sl_seo4`](sl_seo4.md) | Selenate stored in the soil profile | kg/ha |
| [`sl_seo3`](sl_seo3.md) | Selenite stored in the soil profile | kg/ha |
| [`sl_born`](sl_born.md) | Boron stored in the soil profile | kg/ha |
| [`surq_seo4`](surq_seo4.md) | Selenate: surface-runoff transport | kg/ha |
| [`surq_seo3`](surq_seo3.md) | Selenite: surface-runoff transport | kg/ha |
| [`surq_born`](surq_born.md) | Boron: surface-runoff transport | kg/ha |
| [`sedm_seo4`](sedm_seo4.md) | Selenate: sediment-associated transport | kg/ha |
| [`sedm_seo3`](sedm_seo3.md) | Selenite: sediment-associated transport | kg/ha |
| [`sedm_born`](sedm_born.md) | Boron: sediment-associated transport | kg/ha |
| [`latq_seo4`](latq_seo4.md) | Selenate: lateral-flow transport | kg/ha |
| [`latq_seo3`](latq_seo3.md) | Selenite: lateral-flow transport | kg/ha |
| [`latq_born`](latq_born.md) | Boron: lateral-flow transport | kg/ha |
| [`urbq_seo4`](urbq_seo4.md) | Selenate: urban-runoff transport | kg/ha |
| [`urbq_seo3`](urbq_seo3.md) | Selenite: urban-runoff transport | kg/ha |
| [`urbq_born`](urbq_born.md) | Boron: urban-runoff transport | kg/ha |
| [`wetq_seo4`](wetq_seo4.md) | Selenate: wetland-outflow transport | kg/ha |
| [`wetq_seo3`](wetq_seo3.md) | Selenite: wetland-outflow transport | kg/ha |
| [`wetq_born`](wetq_born.md) | Boron: wetland-outflow transport | kg/ha |
| [`tile_seo4`](tile_seo4.md) | Selenate: tile-flow transport | kg/ha |
| [`tile_seo3`](tile_seo3.md) | Selenite: tile-flow transport | kg/ha |
| [`tile_born`](tile_born.md) | Boron: tile-flow transport | kg/ha |
| [`perc_seo4`](perc_seo4.md) | Selenate: percolation | kg/ha |
| [`perc_seo3`](perc_seo3.md) | Selenite: percolation | kg/ha |
| [`perc_born`](perc_born.md) | Boron: percolation | kg/ha |
| [`gwup_seo4`](gwup_seo4.md) | Selenate: groundwater-to-soil transfer | kg/ha |
| [`gwup_seo3`](gwup_seo3.md) | Selenite: groundwater-to-soil transfer | kg/ha |
| [`gwup_born`](gwup_born.md) | Boron: groundwater-to-soil transfer | kg/ha |
| [`wtsp_seo4`](wtsp_seo4.md) | Selenate: wetland seepage | kg/ha |
| [`wtsp_seo3`](wtsp_seo3.md) | Selenite: wetland seepage | kg/ha |
| [`wtsp_born`](wtsp_born.md) | Boron: wetland seepage | kg/ha |
| [`irsw_seo4`](irsw_seo4.md) | Selenate: surface-water irrigation | kg/ha |
| [`irsw_seo3`](irsw_seo3.md) | Selenite: surface-water irrigation | kg/ha |
| [`irsw_born`](irsw_born.md) | Boron: surface-water irrigation | kg/ha |
| [`irgw_seo4`](irgw_seo4.md) | Selenate: groundwater irrigation | kg/ha |
| [`irgw_seo3`](irgw_seo3.md) | Selenite: groundwater irrigation | kg/ha |
| [`irgw_born`](irgw_born.md) | Boron: groundwater irrigation | kg/ha |
| [`irwo_seo4`](irwo_seo4.md) | Selenate: outside-watershed irrigation | kg/ha |
| [`irwo_seo3`](irwo_seo3.md) | Selenite: outside-watershed irrigation | kg/ha |
| [`irwo_born`](irwo_born.md) | Boron: outside-watershed irrigation | kg/ha |
| [`rain_seo4`](rain_seo4.md) | Selenate: wet deposition | kg/ha |
| [`rain_seo3`](rain_seo3.md) | Selenite: wet deposition | kg/ha |
| [`rain_born`](rain_born.md) | Boron: wet deposition | kg/ha |
| [`dryd_seo4`](dryd_seo4.md) | Selenate: dry deposition | kg/ha |
| [`dryd_seo3`](dryd_seo3.md) | Selenite: dry deposition | kg/ha |
| [`dryd_born`](dryd_born.md) | Boron: dry deposition | kg/ha |
| [`fert_seo4`](fert_seo4.md) | Selenate: fertilizer input | kg/ha |
| [`fert_seo3`](fert_seo3.md) | Selenite: fertilizer input | kg/ha |
| [`fert_born`](fert_born.md) | Boron: fertilizer input | kg/ha |
| [`uptk_seo4`](uptk_seo4.md) | Selenate: plant uptake | kg/ha |
| [`uptk_seo3`](uptk_seo3.md) | Selenite: plant uptake | kg/ha |
| [`uptk_born`](uptk_born.md) | Boron: plant uptake | kg/ha |
| [`rctn_seo4`](rctn_seo4.md) | Selenate: soil reaction | kg/ha |
| [`rctn_seo3`](rctn_seo3.md) | Selenite: soil reaction | kg/ha |
| [`rctn_born`](rctn_born.md) | Boron: soil reaction | kg/ha |
| [`sorb_seo4`](sorb_seo4.md) | Selenate: soil sorption | kg/ha |
| [`sorb_seo3`](sorb_seo3.md) | Selenite: soil sorption | kg/ha |
| [`sorb_born`](sorb_born.md) | Boron: soil sorption | kg/ha |
| [`conc_seo4`](conc_seo4.md) | Selenate: soil-water concentration | g/m3 |
| [`conc_seo3`](conc_seo3.md) | Selenite: soil-water concentration | g/m3 |
| [`conc_born`](conc_born.md) | Boron: soil-water concentration | g/m3 |
| [`seo4_srbd`](seo4_srbd.md) | Selenate: sorbed constituent mass | kg/ha |
| [`seo3_srbd`](seo3_srbd.md) | Selenite: sorbed constituent mass | kg/ha |
| [`born_srbd`](born_srbd.md) | Boron: sorbed constituent mass | kg/ha |

## Routing unit

The `rout_unit_cs_*` files report these exact three-heading groups:

- `total_seo4`, `total_seo3`, `total_born`; `perc_seo4`, `perc_seo3`, `perc_born`; `surq_seo4`, `surq_seo3`, `surq_born`; `latq_seo4`, `latq_seo3`, `latq_born`; `tile_seo4`, `tile_seo3`, `tile_born`; `sedm_seo4`, `sedm_seo3`, `sedm_born`; and `wtsp_seo4`, `wtsp_seo3`, `wtsp_born`.
- `irsw_seo4`, `irsw_seo3`, `irsw_born`; `irgw_seo4`, `irgw_seo3`, `irgw_born`; and `irwo_seo4`, `irwo_seo3`, `irwo_born`.
- `rain_seo4`, `rain_seo3`, `rain_born`; `dryd_seo4`, `dryd_seo3`, `dryd_born`; and `fert_seo4`, `fert_seo3`, `fert_born`.
- `uptk_seo4`, `uptk_seo3`, `uptk_born`; `rctn_seo4`, `rctn_seo3`, `rctn_born`; and `sorb_seo4`, `sorb_seo3`, `sorb_born`.

Masses are reported in kg.

## Channel

The `channel_cs_*` files contain these exact groups: `seo4_in`, `seo3_in`, `born_in`; `seo4_gw`, `seo3_gw`, `born_gw`; `seo4_out`, `seo3_out`, `born_out`; `seo4_seep`, `seo3_seep`, `born_seep`; `seo4_irr`, `seo3_irr`, `born_irr`; `seo4_div`, `seo3_div`, `born_div`; `seo4_mass`, `seo3_mass`, `born_mass`; and `seo4_conc`, `seo3_conc`, `born_conc`. Masses are kg and concentrations are g/m3.

## Aquifer

The `aquifer_cs_*` files contain groups for groundwater storage (`gw_seo4`, `gw_seo3`, `gw_born`), recharge (`rchg_seo4`, `rchg_seo3`, `rchg_born`), seepage, irrigation, diversion, sorption, reaction, mass, concentration, and sorbed mass. The exact remaining headings are `seep_seo4`, `seep_seo3`, `seep_born`; `irr_seo4`, `irr_seo3`, `irr_born`; `div_seo4`, `div_seo3`, `div_born`; `sorb_seo4`, `sorb_seo3`, `sorb_born`; `rctn_seo4`, `rctn_seo3`, `rctn_born`; `mass_seo4`, `mass_seo3`, `mass_born`; `conc_seo4`, `conc_seo3`, `conc_born`; and `srbd_seo4`, `srbd_seo3`, `srbd_born`.

## Reservoir and wetland

The `reservoir_cs_*` and `wetland_cs_*` files share one schema. After the identifying columns they print these exact three-heading groups: `seo4_in`, `seo3_in`, `born_in`; `seo4_out`, `seo3_out`, `born_out`; `seo4_seep`, `seo3_seep`, `born_seep`; `seo4_setl`, `seo3_setl`, `born_setl`; `seo4_rctn`, `seo3_rctn`, `born_rctn`; `seo4_prod`, `seo3_prod`, `born_prod`; `seo4_fert`, `seo3_fert`, `born_fert`; `seo4_irrg`, `seo3_irrg`, `born_irrg`; `seo4_div`, `seo3_div`, `born_div`; `seo4_mass`, `seo3_mass`, `born_mass`; and `seo4_conc`, `seo3_conc`, `born_conc`. The final heading is `vol_m3`.

## Basin balance

The `basin_cs_*` files begin with `yr`, `mo`, and `jday`, then print one full process block for each constituent:

- Selenate: `latq_seo4`, `surq_seo4`, `sedm_seo4`, `urbq_seo4`, `wetq_seo4`, `tile_seo4`, `perc_seo4`, `gwup_seo4`, `wtsp_seo4`, `irsw_seo4`, `irgw_seo4`, `irwo_seo4`, `rain_seo4`, `dryd_seo4`, `fert_seo4`, `uptk_seo4`, `rct_sl_seo4`, `srb_sl_seo4`, `ptso_seo4`, `ptout_seo4`, `dis_sl_seo4`, `sbd_sl_seo4`, `gw_seo4`, `rchg_seo4`, `seep_seo4`, `rct_aq_seo4`, `srb_aq_seo4`, `dis_aq_seo4`, and `sbd_aq_seo4`.
- Selenite: `latq_seo3`, `surq_seo3`, `sedm_seo3`, `urbq_seo3`, `wetq_seo3`, `tile_seo3`, `perc_seo3`, `gwup_seo3`, `wtsp_seo3`, `irsw_seo3`, `irgw_seo3`, `irwo_seo3`, `rain_seo3`, `dryd_seo3`, `fert_seo3`, `uptk_seo3`, `rct_sl_seo3`, `srb_sl_seo3`, `ptso_seo3`, `ptout_seo3`, `dis_sl_seo3`, `sbd_sl_seo3`, `gw_seo3`, `rchg_seo3`, `seep_seo3`, `rct_aq_seo3`, `srb_aq_seo3`, `dis_aq_seo3`, and `sbd_aq_seo3`.
- Boron: `latq_born`, `surq_born`, `sedm_born`, `urbq_born`, `wetq_born`, `tile_born`, `perc_born`, `gwup_born`, `wtsp_born`, `irsw_born`, `irgw_born`, `irwo_born`, `rain_born`, `dryd_born`, `fert_born`, `uptk_born`, `rct_sl_born`, `srb_sl_born`, `ptso_born`, `ptout_born`, `dis_sl_born`, `sbd_sl_born`, `gw_born`, `rchg_born`, `seep_born`, `rct_aq_born`, `srb_aq_born`, `dis_aq_born`, and `sbd_aq_born`.
