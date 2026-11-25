---
description: Regional land-use water-balance and sediment targets for soft calibration.
---

# water\_balance.sft

Supplies regional average annual water-balance ratios and sediment yield targets for soft calibration, read by [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L35-L102) into `region` and `lscal` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L150)).

## Region count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mreg](mreg.md) | Number of soft-calibration regions | integer | — | — | > 0 |

## Region header

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Region name (`basin` applies basin-wide) | string | — | — | — |
| [nlum](nlum.md) | Number of land-use target records in the region | integer | — | — | > 0 |

## Land-use targets

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_2.md) | Land-use calibration group name (`basin` matches all HRUs) | string | — | `default` | — |
| [srr](srr.md) | Surface runoff ratio ($Q_{\text{surf}} / P$) | real | — | 0 | 0–1 |
| [lfr](lfr.md) | Lateral soil flow ratio ($Q_{\text{lat}} / P$) | real | — | 0 | 0–1 |
| [pcr](pcr.md) | Percolation ratio ($Q_{\text{perc}} / P$) | real | — | 0 | 0–1 |
| [etr](etr.md) | Evapotranspiration ratio ($\text{ET} / P$) | real | — | 0 | 0–1 |
| [tfr](tfr.md) | Tile flow ratio ($Q_{\text{tile}} / P$) | real | — | 0 | 0–1 |
| [pet](pet.md) | Average annual potential ET target (parsed but unused) | real | mm/yr | 0 | — |
| [sed](sed.md) | Average annual land-phase sediment yield target | real | t/ha | 0 | >= 0 |
| [wyr](wyr.md) | Total water yield ratio ($\text{WYLD} / P$, used in `b`/`y` mode) | real | — | 0 | 0–1 |
| [bfr](bfr.md) | Baseflow ratio (fraction of water yield in `b`/`y` mode) | real | — | 0 | 0–1 |
| [solp](solp.md) | Average annual soluble phosphorus yield target (parsed but unused) | real | kg/ha | 0 | — |

When `hyd_hru` in `codes.sft` is not `"a"` (for example `"b"` or `"y"`), [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L92-L96) derives the precipitation-normalized targets from `wyr` ($f_{\text{wyr}}$) and `bfr` ($f_{\text{bfr}}$):

$$f_{\text{srr}} = f_{\text{wyr}}(1 - f_{\text{bfr}}), \qquad f_{\text{bfr}}' = f_{\text{wyr}}\,f_{\text{bfr}}, \qquad f_{\text{lfr}} = 0.1\,f_{\text{bfr}}'$$

where:
- $f_{\text{srr}}$ is the derived `srr` target (dimensionless),
- $f_{\text{bfr}}'$ is the converted baseflow fraction of precipitation (dimensionless),
- $f_{\text{lfr}}$ is the derived `lfr` target (dimensionless),
- $f_{\text{wyr}}$ is `wyr` (dimensionless), and
- $f_{\text{bfr}}$ is `bfr` (dimensionless).

After accumulating baseline averages, [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L48-L52) and [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L68-L72) multiply `srr`, `lfr`, `pcr`, `etr`, and `tfr` by saved average annual precipitation (`precip_aa_sav`) to convert ratios to depth targets in mm.
