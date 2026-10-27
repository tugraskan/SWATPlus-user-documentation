---
description: This file contains the filter strip parameters.
---

# filterstrip.str

A filter strip is a strip of dense vegetation located to intercept runoff from upslope pollutant sources and filter it. Filter strips remove contaminants by reducing overland flow velocity which results in the deposition of particulates. The filter strip area also acts as an area of increased infiltration, reducing both the runoff volume and non-particulate contaminants. The filter strip algorithm used in SWAT+ was derived from White and Arnold (2009). Filter strips reduce sediment, nutrients, bacteria, and pesticides, but do not affect surface runoff in SWAT+.

| Field                  | Description                                                              | Type    | Unit     | Range     |
| ---------------------- | ------------------------------------------------------------------------ | ------- | -------- | --------- |
| [name](name_fsdb.md)   | Name of filter strip record                                              | ​string | ​n/a     | n/a       |
| flag\* | On/off flag for vegetative filter strip (0 = off; positive = on) | integer | n/a | 0-1 |
| [fld\_vfs](fld_vfs.md)\* | ​Ratio of field area to filter strip area                                | real    | ratio    | 0.0-300.0 |
| [con\_vfs](con_vfs.md)\* | ​Fraction of flow entering the most concentrated 10% of the filter strip | real    | fraction | 0.25-0.75 |
| [cha\_q](cha_q.md)\* | Fraction of flow in the most concentrated 10% of the filter strip that is fully channelized | real | fraction | 0.0-0.95 |

\* Input-file labels marked with an asterisk have different Fortran names: `flag` → `filtstrip_db(ifiltop)%vfsi`; `fld_vfs` → `filtstrip_db(ifiltop)%vfsratio`; `con_vfs` → `filtstrip_db(ifiltop)%vfscon`; `cha_q` → `filtstrip_db(ifiltop)%vfsch`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/scen_read_filtstrip.f90#L45).

#### References:

> White, Michael J. and Arnold, Jeff G. (2009): Development of a simplistic vegetative filter strip model for sediment and nutrient retention at the field scale. Hydrological Processes 23, 1602– 1616. DOI: 10.1002/hyp.7291
