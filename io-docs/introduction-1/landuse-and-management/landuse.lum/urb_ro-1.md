---
description: Urban runoff simulation option
---

# urb\_ro

**Code reference:** `lum(ilu)%urb_ro`

**Declared type:** `land_use_management` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/landuse_read.f90#L56), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/landuse_data_module.f90#L13)).

Most large watersheds and river basins contain areas of urban land use. Estimates of the quantity and quality of runoff in urban areas are required for comprehensive management analysis. SWAT+ calculates runoff from urban areas with the SCS curve number method or the Green & Ampt equation. Loadings of sediment and nutrients are determined using one of two options. The first is a set of linear regression equations developed by the USGS (Driver and Tasker, 1988) for estimating storm runoff volumes and constituent loads. The other option is to simulate the build-up and wash-off mechanisms, similar to SWMM (Storm Water Management Model; Huber and Dickinson, 1988).&#x20;

| Option            | Description                 |
| ----------------- | --------------------------- |
| usgs\_reg         | USGS regression equations   |
| buildup\_washoff  | build-up/wash-off algorithm |

#### References

> Driver and Tasker (1988)
>
> Huber and Dickinson (1988)
