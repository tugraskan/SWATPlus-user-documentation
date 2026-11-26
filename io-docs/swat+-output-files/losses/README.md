# Losses

Losses output can be printed at basin, LSU, HRU, and HRU-lte level by entering "y" in the _basin\_ls_, _lsunit\_ls_, _hru\_ls_, and _hru-lte\_ls_ lines in [print.prt](../../introduction-1/simulation-settings/print.prt), respectively. Losses output can be printed at daily, monthly, yearly, and average annual time steps. The names of the losses output files are as follows:&#x20;

* basin\_ls\_day.txt
* basin\_ls\_mon.txt
* basin\_ls\_yr.txt
* basin\_ls\_aa.txt
* lsunit\_ls\_day.txt
* lsunit\_ls\_mon.txt
* lsunit\_ls\_yr.txt
* lsunit\_ls\_aa.txt
* hru\_ls\_day.txt
* hru\_ls\_mon.txt
* hru\_ls\_yr.txt
* hru\_ls\_aa.txt
* hru-lte\_ls\_day.txt
* hru-lte\_ls\_mon.txt
* hru-lte\_ls\_yr.txt
* hru-lte\_ls\_aa.txt

Set `csvout` to `y` for CSV copies. Daily rows also follow the daily print window and interval. All 32 variants print 22 headings and a 22-entry units record. The shared header includes `plant_cov`, `mgt_ops`, and `percn`. Only full HRU rows write those three values. Basin, LSU, and HRU-LTE rows have 19 values and stop at `satexn`. [Daily print timing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L194), [Heading and units declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L422)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Julian day | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of the month | n/a |
| [yr](yr.md) | Year | n/a |
| [unit](unit.md) | ID of the object | n/a |
| [gis_id](gis_id.md) | Object ID in GIS | n/a |
| [name](name.md) | Name of the object or SWAT+ setup (basin outputs) | n/a |
| [sedyld](sedyld.md) | Final reported sediment yield per unit area | t/ha |
| [sedorgn](sedorgn.md) | Organic nitrogen carried with sediment after routing and active conservation practices | kg N/ha |
| [sedorgp](sedorgp.md) | Organic phosphorus transported in surface runoff | kg/ha |
| [surqno3](surqno3.md) | Nitrate nitrogen transported in surface runoff | kg/ha |
| [lat3no3](lat3no3.md) | Nitrate nitrogen transported in lateral flow | kg/ha |
| [surqsolp](surqsolp.md) | Soluble phosphorus transported in surface runoff | kg/ha |
| [usle](usle.md) | Soil erosion predicted with the USLE equation | t/ha |
| [sedminp](sedminp.md) | Mineral phosphorus leaving the landscape attached to sediment | kg/ha |
| [tileno3](tileno3.md) | Nitrate nitrogen transported in tile flow | kg/ha |
| [lchlabp](lchlabp.md) | Soluble (labile) phosphorus leaching past bottom soil layer | kg/ha |
| [tilelabp](tilelabp.md) | Soluble (labile) phosphorus in tile flow | kg/ha |
| [satexn](satexn.md) | Saturation-excess nitrate slot. The current source leaves it at zero | kg N/ha |
| [plant_cov](plant_cov.md) | Plant-cover label written for HRU rows | n/a |
| [mgt_ops](mgt_ops.md) | Management-operation label written for HRU rows | n/a |
| [percn](percn.md) | HRU nitrate transported by percolation; header-only at other levels | kg N/ha |

## Where the daily values come from

| Fields | Daily source and adjustments |
| --- | --- |
| `sedyld`, `usle` | The full HRU divides its final sediment yield by HRU area. That yield can include routed sediment, lateral and tile sediment, and wetland release. Surface storage, urban routines, and conservation practices can change the yield before it is reported. `usle` is the separate erosion estimate from `ero_ysed`. [HRU sequence](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L311-L338), [lateral and tile sediment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_latsed.f90#L32-L52), [reported yield and USLE](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L871-L885). |
| `sedorgn`, `sedorgp`, `sedminp` | The static and SWAT-C routines produce sediment-associated N, and `nut_psed` produces the P components. The reported `sedminp` adds active and stable mineral P. The wetland routine splits released soluble P between those two mineral slots. The [management settings](#how-management-changes-reported-losses) describe which practices alter these values. [nutrient dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L524-L541), [sediment P fractions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_psed.f90#L66-L86), [wetland nutrient routing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L253-L268), [urban BMP](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urb_bmp.f90#L42-L50). |
| `surqno3`, `lat3no3`, `tileno3`, `percn` | `nut_nlch` calculates surface nitrate from the top layer and sums lateral nitrate across layers. Positive tile flow draws nitrate from the drain layer and the layers below it. Bottom-layer nitrate percolation is printed as HRU `percn`. The surface, lateral, and tile nitrate values can change in storage and routing before the HRU copies them into the losses record. The saturated-buffer branch can also divert part of the tile nitrate. [nitrate transport](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L69-L148), [surface release](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/stor_surfstor.f90#L196-L201), [subsurface release](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_substor.f90#L52-L73), [saturated buffer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L642-L652). |
| `surqsolp`, `lchlabp`, `tilelabp` | `nut_solp` starts these values from the soil labile P pool. The reported surface value is copied after surface lag and any later adjustments. The bottom-layer and tile fields retain the values assigned in `nut_solp`. That routine skips the layer indexed by `i_sep(j)`, including the tile or bottom calculation if it occurs in that layer. [P transport and layer skip](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_solp.f90#L58-L100), [final surface-P assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L877-L885). |
| `satexn` | The daily record defaults to zero. No active producer assigns its saturation-excess nitrate field in this revision. [record default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L151-L164), [HRU record assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L871-L885). |

In the sediment P calculation, `nut_psed` counts the top-layer manure P pool twice in the attached-P sum and organic fraction. It uses stable P to calculate the active fraction and active P to calculate the stable fraction, then caps and subtracts each loss from the pool named by its output component. [fractions, caps, and soil pool changes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_psed.f90#L56-L86).

## How management changes reported losses

Land-use records and decision-table actions can assign the filter strip, grassed waterway, and fixed-efficiency BMP. The daily HRU runs them in that order after surface and subsurface lagging. [Land-use structure initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_init.f90#L12-L32), [Decision-table actions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1183-L1253), [Daily order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L598-L621)

| Configuration | Effect on Losses |
| --- | --- |
| Filter strip (`fstrip`) | A positive `vfsi` calls the filter. The filter applies calculated reductions to sediment, sediment organic N, sediment P, surface nitrate, and soluble surface P. [Setting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L51-L68), [Filter calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_filter.f90#L130-L231) |
| Grassed waterway (`grassww`) | A linked structure enables the routine. It scales sediment, sediment organic N, and all three sediment P components by the outgoing sediment fraction. It scales surface nitrate and soluble P by the outgoing runoff fraction. [Setting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L70-L104), [Loss updates](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_grass_wway.f90#L169-L186) |
| Fixed BMP (`user_def`) | Each configured [bmpuser.str](../../introduction-1/structural-practices/bmpuser.str/README.md) efficiency multiplies its load by `1 − efficiency`. Particulate P applies to organic, active mineral, and stable mineral P. The soluble efficiencies apply to surface nitrate and soluble surface P. [Setting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L106-L113), [Load updates](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_bmpfixed.f90#L42-L60) |
| Saturated buffer | The source-HRU branch partitions tile nitrate by the configured source fraction and the Losses row uses the remaining share. This is separate from the filter-strip buffer routine. [Tile nitrate split](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L637-L653) |

The filter-strip buffer requires positive `filterw`, and the urban BMP call requires a positive sum of five concentration caps. In this revision those variables are initialized to zero and have no active nonzero assignment, so these two branches stay inactive through the standard model inputs. The urban routine contains a dormant assignment that would overwrite sediment organic N with a value from the particulate-P cap if the branch were activated. The separate urban load-generation routines can still run. [Initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/zero0.f90#L35-L70), [Call gates](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L589-L621), [Urban BMP gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L661-L667), [Dormant assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urb_bmp.f90#L42-L50)

## Reporting levels and periods

The four reporting levels omit a final partial month from yearly and average-annual loss totals. The full-HRU `percn` column follows the same boundary because it comes from the plant-and-weather accumulator. [HRU month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L100-L106), [year transfer and annual percolation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L169-L180), [average-annual percolation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L274-L281).

- **Full HRU.** The writer appends the current plant-cover and management labels and the nitrate leaching value from the matching plant-and-weather record. The loss-file switch controls this write independently of the plant-and-weather file switch. [Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L80), [Average-annual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L274)
- **HRU-LTE.** Sediment yield is calculated by the LTE producer. The other eleven loss fields are either explicitly set to zero or left at their zero defaults in this source revision. [LTE producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L392), [Record defaults](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L151)
- **Landscape unit and basin.** The LSU writer uses element IDs to select daily loss records and weights them by `ru_frac` above `1.e-9`. The basin writer uses the selected object number to look up both the daily record and `bsn_frac` above `1.e-12`. If element IDs and object numbers differ, these lookups can select different records or weights. Basin rows write `1` for both identifiers. [Contributor selection](../plant-and-weather/plant-weather-output.md#landscape-unit-and-basin-contributors)
- **Monthly, yearly, and average annual.** Monthly and yearly rows sum the daily losses. The average-annual writers divide accumulated losses by `time%yrs_prt`. Full-HRU `percn` sums separately and uses the same divisor for average annual output. The units record keeps the base labels in all periods. It prints `tons` for `usle`, although the source calculation is per hectare. [Loss operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L1002), [Annual division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L1287), [USLE calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ysed.f90#L81)
