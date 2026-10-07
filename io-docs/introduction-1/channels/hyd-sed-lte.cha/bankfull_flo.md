---
description: Bankfull flow factor
---

# bankfull\_flo

Factor applied to the channel's flow at bankfull depth (from the channel rating curve) to get the flow above which water spills onto the floodplain.

{% hint style="warning" %}
In SWAT+ 62.0.1 the channel sediment routine resets this value to 1.5 every time it runs, so the value in hyd-sed-lte.cha currently has no effect.
{% endhint %}
