---
description: "Use/treatment name with variant-specific positions"
---

# name

**Code references:** `om_use_name(iuse)` and `om_treat_name(itrt)` ([name arrays](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L217)). These are the names selected by the use/treatment output indices; the field has no physical unit.

| File/row | Actual name position |
| --- | ---: |
| Daily use TXT | 5 |
| Other use TXT and all use CSV | 4 |
| Daily treatment TXT | 6 |
| Other treatment TXT and all treatment CSV | 5 |

The common printed header puts `name` at position 5 for every variant. Treatment writes identifier **before** name; use writes name **before** identifier. All CSV and monthly/yearly/AA TXT omit `jday`, producing 23 values under 24 headings.

See the [water-use](water-use.md) and [water-treatment](water-treatment.md) row variants and CSV routing defects. These identifiers select a process diagnostic, not a POU/POD child index or an effluent flow record.

[Back to the water-use schema](water-use.md) · [Back to the water-treatment schema](water-treatment.md).
