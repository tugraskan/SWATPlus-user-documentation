---
description: Area of the object
---

# area

The table below gives an overview of what the area represents and what it is used for in the model.&#x20;

{% hint style="warning" %}
Even though some objects don't have an area, a value has to be specified in the area column to make sure the file gets read correctly by the model.&#x20;
{% endhint %}

| Object             | Area                           | Use                      |
| ------------------ | ------------------------------ | ------------------------ |
| HRU                | Area of the HRU                | Conversion from mm to m3 |
| Routing Unit       | Area of the Routing Unit       | Conversion from mm to m3 |
| Aquifer            | Area of the aquifer            | Conversion from mm to m3 |
| Channel            | Drainage area of the channel   | n/a                      |
| Reservoir          | Drainage area of the reservoir | n/a                      |
| Outlet             | Object does not have an area   | n/a                      |
| Recall             | Object does not have an area   | n/a                      |
| Export Coefficient | Reference area of the export-coefficient object | Scales per-area values by the routed element area divided by this area |
| Delivery Ratio     | Object does not have an area   | n/a                      |
