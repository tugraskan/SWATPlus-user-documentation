---
description: Number of source objects available for the demand object
---

# srcs

{% hint style="warning" %}
This is a historical `water_allocation.wro` field. For the reviewed main layout, see [place_of_use.wro](../place_of_use.wro.md) and [point_of_diver.wro](../point_of_diver.wro.md). The original description below is retained as historical reference.
{% endhint %}

The sources are listed in order of selection and the fraction from each source is input. The other input is compensation – if other sources are not available, the current source may be allowed to compensate for the demand. The model goes through all sources in the order listed and allocates based on the fractions. The model loops through the sources again, checking to see if compensation is allowed.
