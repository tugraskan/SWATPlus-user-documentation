---
description: Soil water adjustment factor for CN3
---

# cn3\_swf

**Code reference:** `hyd_db(ithyd)%cn3_swf`

**Declared type:** `hydrology_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrol_read.f90#L47), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L17)).

This parameter gives the user control over the level of saturation of the soil that has to be reached before the model switches from using the Curve Number for moisture condition II to moisture condition III. Thus, it can be used to delay the onset of surface runoff after dry periods.

<figure><img src="../../../.gitbook/assets/image (8).png" alt="" width="375"><figcaption><p>The effect of cn3_swf on the Curve Number</p></figcaption></figure>

{% hint style="warning" %}

For an HRU with a tile drain, SWAT+ main (6f515368) sets cn3_swf to 0.95 during initialization, overriding the value entered in hydrology.hyd.

{% endhint %}
