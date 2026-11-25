---
description: "This file contains channel sediment transport and erosion parameters."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains channel sediment transport and erosion parameters.

{% hint style="info" %}
[`proc_cha.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cha.f90#L20-L41) reads `sediment.cha` via [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L1) and initializes bed/bank fractions in [`ch_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_initial.f90#L1), but daily `case ("chan")` routing in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305-L310) is commented out. Active channel sediment routing uses [`hyd-sed-lte.cha`](../hyd-sed-lte.cha/) and [`sed_nut.cha`](../sed_nut.cha/).
{% endhint %}

# sediment.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [eqn](eqn.md) | Selects the sediment transport equation applied to this channel: 0 = original SWAT, 1 = Bagnold, 2 = Kodatie, 3 = Molinas-WU, 4 = Yang | integer | n/a | 0 | 0-4 |
| [cov1](cov1.md) | Channel bank erodibility factor scaling the computed bank critical shear stress | real | none | 0.1 | 0.0-1.0 (eqn=0) / 0.0-25.0 |
| [cov2](cov2.md) | Channel bed cover factor scaling the computed bed critical shear stress | real | none | 0.1 | 0.0-1.0 (eqn=0) / 0.0-25.0 |
| [bnk_bd](bnk_bd.md) | Bulk density of the channel bank sediment | real | g/cm3 | 1.40 | 1.1-1.9 |
| [bed_bd](bed_bd.md) | Bulk density of the channel bed sediment | real | g/cm3 | 1.50 | 1.1-1.9 |
| [bnk_kd](bnk_kd.md) | Jet-test-derived erodibility of the channel bank sediment | real | cm3/(N*s) | 0.2 | — |
| [bed_kd](bed_kd.md) | Jet-test-derived erodibility of the channel bed sediment | real | cm3/(N*s) | 0.2 | — |
| [bnk_d50](bnk_d50.md) | Median (D50) particle size diameter of the channel bank sediment | real | um | 50 | <=10000 |
| [bed_d50](bed_d50.md) | Median (D50) particle size diameter of the channel bed sediment | real | um | 500 | <=10000 |
| [tc_bnk](tc_bnk.md) | Critical shear stress required to initiate motion of the channel bank | real | N/m2 | 0 | — |
| [tc_bed](tc_bed.md) | Critical shear stress required to initiate motion of the channel bed | real | N/m2 | 0 | — |
| [erod(1)](erod_1.md) | Monthly (January) channel erodibility | real | — | — | — |
| [erod(2)](erod_2.md) | Monthly (February) channel erodibility | real | — | — | — |
| [erod(3)](erod_3.md) | Monthly (March) channel erodibility | real | — | — | — |
| [erod(4)](erod_4.md) | Monthly (April) channel erodibility | real | — | — | — |
| [erod(5)](erod_5.md) | Monthly (May) channel erodibility | real | — | — | — |
| [erod(6)](erod_6.md) | Monthly (June) channel erodibility | real | — | — | — |
| [erod(7)](erod_7.md) | Monthly (July) channel erodibility | real | — | — | — |
| [erod(8)](erod_8.md) | Monthly (August) channel erodibility | real | — | — | — |
| [erod(9)](erod_9.md) | Monthly (September) channel erodibility | real | — | — | — |
| [erod(10)](erod_10.md) | Monthly (October) channel erodibility | real | — | — | — |
| [erod(11)](erod_11.md) | Monthly (November) channel erodibility | real | — | — | — |
| [erod(12)](erod_12.md) | Monthly (December) channel erodibility | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
