---
description: >-
  This file supplies named sets of initial salt ion concentrations and mineral
  percentages in HRU soil and plants.
---

# salt\_hru.ini

SWAT+ opens `salt_hru.ini` directly by filename in the simulation working directory via [`salt_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_read.f90#L21-L74) (it does not use `in_init%salt_soil` from `file.cio`). The file begins with **5 header lines** (1 title line plus 4 column-header lines: [`salt_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_read.f90#L24-L32)). Each initialization set consists of three lines: a `name` row, a `soil` row of `cs_db%num_salts + 5` real values, and a `plt` row of `cs_db%num_salts + 5` real values.

For the standard 8 salt ions in [**constituents.cs**](../../constituents/constituents.cs.md), the first `cs_db%num_salts` positions correspond to `SO4`, `Ca`, `Mg`, `Na`, `K`, `Cl`, `CO3`, and `HCO3` (`mg/L`), followed by 5 salt mineral positions (`CaCO3`, `MgCO3`, `CaSO4`, `MgSO4`, and `NaCl` in `%` of soil solid mass).

## Parameter-set name

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |

## Soil values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [soil](soil.md) | Initial soil ion concentrations (`1..num_salts`) and mineral percentages (`+5`) | real | mg/L; % | — | — |

## Plant values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [plt](plt.md) | Intended plant salt values (read into memory, but not used in simulation) | real | — | — | — |
