---
description: Fraction of hydrograph sent to the receiving object
---

# frac

**Code reference:** `ob(i)%frac_out(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L374)).

{% hint style="warning" %}
Fractions should add up to 1 for each hydrograph type. For example, `sur` and `lat` can each be sent with a fraction of 1.0. Otherwise, water is added to or removed from the system. SWAT+ does not check or rescale the fractions.
{% endhint %}

Each connection sends

$$Q_{\text{sent}} = f \times Q_{\text{type}}$$

where $f$ is this fraction and the other term is the sender's hydrograph of the type given in [hyd\_typ](hyd_typ.md) ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L424-L427)). When the receiver is a routing unit, the fraction is also multiplied by each element's fraction for the elements in that unit ([`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L383-L399)).
