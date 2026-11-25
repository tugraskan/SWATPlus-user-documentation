---
description: "Numeric temperature component"
---

# null

**Code references:** `wal_use_omd(iuse)%temp` and `wal_tr_omd(itrt)%temp`, the daily use and treatment record components ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49); [use writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L19); [treatment writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treat_output.f90#L19)).

**Unit:** deg C. The units row is blank, but the record contains a numeric `temp` component. Its physical interpretation is limited by the operations below.

The literal heading `null` labels the final temperature component in daily TXT. It is not a separator or a missing-value marker. Use subtraction keeps the left-hand (outflow) temperature; it does not calculate a temperature difference. Treatment addition/subtraction likewise uses hydrograph temperature rules, so this is not a validated temperature of the material removed. Period addition uses volume-weighted temperature when combined flow exceeds 1e-6 and zero otherwise; division by `time%yrs_prt` leaves temperature unchanged.

**Position warning:** The printed heading is at position 24, but only daily TXT includes all six prefix values. In all CSV rows and monthly/yearly/AA TXT, the omitted `jday` moves this component to position 23. There is no value at printed position 24 in those 23-value rows; the numeric temperature is at position 23. Daily treatment TXT also reverses name and identifier, while its numeric tail retains the daily TXT positions.

See the [water-use](water-use.md) and [water-treatment](water-treatment.md) row variants, CSV routing defects, and diagnostic limits. **Producer references:** [use difference](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L68); [treatment removal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L79); [subtraction](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1366), [addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337), [division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1478).

[Back to the water-use schema](water-use.md) · [Back to the water-treatment schema](water-treatment.md).
