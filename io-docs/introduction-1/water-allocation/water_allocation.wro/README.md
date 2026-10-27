---
description: This file contains water allocation tables.
---

# water\_allocation.wro

{% hint style="warning" %}
This page preserves the historical `water_allocation.wro` layout. It is not the input layout used by the reviewed SWAT+ main `6f515368` reader. For the current formats, use [place_of_use.wro](../place_of_use.wro.md) and [point_of_diver.wro](../point_of_diver.wro.md). The historical field descriptions below must not be used as instructions for those files.
{% endhint %}

The current defaults are declared in [input_file_module.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/input_file_module.f90#L144).

## Historical format

The structure of the water allocation file is different than that of most other SWAT+ input files. As usual, the first line is reserved for a title. The second line in the file specifies the total number of water allocation tables included in the file.&#x20;

Each water allocation table has three parts, which all have their own headers. First, the name of the water allocation table, the rule type, the number of source and demand objects, and whether or not one of the source objects is a channel are specified. &#x20;

<table><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th></tr></thead><tbody><tr><td>name</td><td>Name of the water allocation table</td><td>string</td></tr><tr><td><a href="rule_typ.md">rule_typ</a></td><td>Rule type to allocate water</td><td>string</td></tr><tr><td>src_obs</td><td>Number of source objects</td><td>integer</td></tr><tr><td>dmd_obs</td><td>Number of demand objects</td><td>integer</td></tr><tr><td><a href="cha_ob.md">cha_ob</a></td><td>Channel as source object</td><td>string</td></tr></tbody></table>

Next, the source objects and their monthly limits are defined. Source objects can be channels, reservoirs, aquifers, or an unlimited source. There needs to be one line per source object.

<table><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th></tr></thead><tbody><tr><td>num</td><td>Source object number</td><td>integer</td></tr><tr><td><a href="ob_typ-source.md">ob_typ</a></td><td>Object type of the source object</td><td>string</td></tr><tr><td>ob_num</td><td>ID of the source object</td><td>integer</td></tr><tr><td><a href="limit_mon.md">limit_mon</a></td><td>Monthly limits</td><td>real</td></tr></tbody></table>

Finally, the demand objects are defined. Demand can be irrigation demand from an HRU, municipal demand, or demand to transfer to another object.There needs to be one line per demand object.

<table data-full-width="false"><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th></tr></thead><tbody><tr><td>num</td><td>Demand object number</td><td>integer</td></tr><tr><td><a href="ob_typ-demand.md">ob_typ</a></td><td>Object type of the demand object</td><td>string</td></tr><tr><td>ob_num</td><td>ID of the demand object</td><td>integer</td></tr><tr><td><a href="withdr.md">withdr</a></td><td>Withdrawal type</td><td>string</td></tr><tr><td><a href="amount.md">amount</a></td><td>Withdrawal amount</td><td>real</td></tr><tr><td><a href="right.md">right</a></td><td>Water right</td><td>string</td></tr><tr><td>treat_typ</td><td>Currently not functional</td><td>string</td></tr><tr><td>treatment</td><td>Currently not functional</td><td>string</td></tr><tr><td><a href="rcv_ob.md">rcv_ob</a></td><td>Object type of the receiving object</td><td>string</td></tr><tr><td><a href="rcv_num.md">rcv_num</a></td><td>ID of the receiving object</td><td>integer</td></tr><tr><td>rcv_dtl</td><td>Currently not used</td><td>string</td></tr><tr><td><a href="srcs.md">srcs</a></td><td>Number of source objects available for the demand object</td><td>integer</td></tr><tr><td><a href="src.md">src</a></td><td>Source object ID</td><td>integer</td></tr><tr><td><a href="frac.md">frac</a></td><td>Fraction of demand to be met by source object</td><td>real</td></tr><tr><td><a href="comp.md">comp</a></td><td>Compensation from source object</td><td>string</td></tr></tbody></table>
