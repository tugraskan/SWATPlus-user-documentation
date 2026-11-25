---
description: "Optional measured soil test results that override soils.sol values for the depths they cover (SWAT+ dev, carbon = 2 only)."
---

# soil\_test.sol

New on SWAT+ dev. Measured soil properties for named soils, which replace the [soils.sol](../soils.sol/README.md) values over the depths they cover. The file is read only when [carbon](../../basin-1/codes.bsn/carbon.md) in codes.bsn is `2` and the file exists in the run folder; it has no entry in [file.cio](../../master-file-file.cio.md) ([`soil_test_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_test_read.f90#L56-L69)).

The file has a title line, a heading line, and one row per tested layer. Blank lines and lines starting with `#` are skipped ([`soil_test_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_test_read.f90#L78-L134)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| soil\_name | Soil name; must match a name in soils.sol | string | n/a | — | — |
| depth\_mm | Depth of the bottom of the tested layer; the layer starts at the previous row's depth for the same soil, or at 0 | real | mm | — | > 0 |
| bd | Bulk density, or `-1` if not measured | real | Mg/m³ | — | — |
| cbn | Organic carbon, or `-1` if not measured | real | % | — | — |
| sand | Sand content, or `-1` if not measured | real | % | — | — |
| silt | Silt content, or `-1` if not measured | real | % | — | — |
| clay | Clay content, or `-1` if not measured | real | % | — | — |

## Rules checked when the file is read

The run stops with an error naming the row if ([`soil_test_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_test_read.f90#L138-L204)):

- a row cannot be read as the seven values above;
- `depth_mm` is not greater than 0;
- rows for one soil are not in ascending depth order, or are not contiguous in the file;
- sand, silt and clay are all given and do not add up to 100 (±0.01).

A soil name that is not in soils.sol gives a warning in `diagnostics.out`, and that row is ignored. A file with no data rows gives a warning and changes nothing.

## How the values are applied

For each soil named in the file, [`soils_test_adjust.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_test_adjust.f90#L22-L109) (called from [`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L281)):

1. expands the soils.sol profile to 1 mm slices;
2. in each tested layer, replaces every measured property (`-1` leaves the soils.sol value) in the slices between the layer's top and bottom depth; depths below the bottom of the soils.sol profile are ignored;
3. sets each model soil layer's bulk density, organic carbon, sand, silt and clay to the average of its slices, weighted by thickness.

Other soil properties (available water capacity, conductivity, rock, and so on) are not changed.
