---
description: "Use or treatment index with variant-specific positions"
---

# use

**Code references:** `iuse` in [the use loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L13) and `itrt` in [the treatment loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treat_output.f90#L13). The printed label `use` identifies a water-use index in use files and a treatment-object index in treatment files. It has no physical unit.

| File/row | Actual identifier position |
| --- | ---: |
| Daily use TXT | 6 |
| Other use TXT and all use CSV | 5 |
| Daily treatment TXT | 5 |
| Other treatment TXT and all treatment CSV | 4 |

The common printed header puts `use` at position 6. Treatment writes identifier before name, reversing the printed order. All CSV and monthly/yearly/AA TXT omit `jday`, causing a further one-position shift.

See the [water-use](water-use.md) and [water-treatment](water-treatment.md) row variants and CSV routing defects. These identifiers select a process diagnostic, not a POU/POD child index or an effluent flow record.

[Back to the water-use schema](water-use.md) · [Back to the water-treatment schema](water-treatment.md).
