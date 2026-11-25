---
description: "Sand-mass change/removal"
---

# san

**Code references:** `wal_use_omd(iuse)%san` and `wal_tr_omd(itrt)%san`, the daily use and treatment record components ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L43); [use writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L19); [treatment writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treat_output.f90#L19)).

**Unit:** tons.

Sand-mass change/removal. For water use, the diagnostic is outflow minus stored inflow: positive means net addition and negative means net removal. For treatment, the diagnostic adds allocated stored inflow minus treated outflow across receiving points. These are process change/removal diagnostics, not the entire routed effluent. Monthly/yearly values sum the daily diagnostic volumes or masses; average annual divides the accumulated yearly values by `time%yrs_prt`.

**Position warning:** The printed heading is at position 18, but only daily TXT includes all six prefix values. In all CSV rows and monthly/yearly/AA TXT, the omitted `jday` moves this component to position 17. At printed position 18, those 23-value rows actually contain `hyd_output%sil`. Daily treatment TXT also reverses name and identifier, while its numeric tail retains the daily TXT positions.

The use producer assigns its daily record; the treatment producer resets its daily record on entry. Repeated calls for the same object do not guarantee a sum across all calls. The output writers then accumulate and clear the resulting daily record.

See the [water-use](water-use.md) and [water-treatment](water-treatment.md) row variants, CSV routing defects, and diagnostic limits. **Producer references:** [use difference](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L68); [treatment removal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L79); [subtraction](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1366), [addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337), [division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1478).

[Back to the water-use schema](water-use.md) · [Back to the water-treatment schema](water-treatment.md).
