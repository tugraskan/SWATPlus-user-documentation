---
description: Withdrawal type
---

# withdr

{% hint style="warning" %}
This is a historical `water_allocation.wro` field. For the reviewed main layout, see [place_of_use.wro](../place_of_use.wro.md) and [point_of_diver.wro](../point_of_diver.wro.md). The original description below is retained as historical reference.
{% endhint %}

Depending on the demand object type, different withdrawal types can be used. For irrigation or transfer decision tables, the name of the table should be entered in this column, for a recall file, the name of the file should be entered, and for average daily withdrawal, "ave\_day" should be entered .

| Withdrawal type       | Description                           | Demand object type |
| --------------------- | ------------------------------------- | ------------------ |
| Name of irrigation DT | Irrigation decision table             | hru                |
| "ave\_day"            | Average daily withdrawal              | muni, divert       |
| Name of recall file   | Daily, monthly, or yearly recall file | muni, divert       |
| Name of transfer DT   | Transfer decision table               | muni, divert       |
