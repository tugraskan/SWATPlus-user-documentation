---
description: This file lists all elements that are part of a Routing Unit.
---

# rout\_unit.ele

<table><thead><tr><th width="108.66664632161456">Field</th><th width="320.00006103515625">Description</th><th width="84">Type</th></tr></thead><tbody><tr><td><a href="id-rout_unit.ele.md">id</a><sup>*</sup></td><td>ID of the element</td><td>integer</td></tr><tr><td><a href="name-rout_uni.ele.md">name</a></td><td>Name of the element</td><td>string</td></tr><tr><td><a href="obj_typ.md">obj_typ</a><sup>*</sup></td><td>Object type of the element</td><td>string</td></tr><tr><td><a href="obj_id.md">obj_id</a><sup>*</sup></td><td>Object ID of the element</td><td>integer</td></tr><tr><td><a href="frac.md">frac</a></td><td>Fraction/ expansion factor of element in Routing Unit</td><td>real</td></tr><tr><td><a href="dlr-rout_unit.ele.md">dlr</a><sup>*</sup></td><td>Delivery ratio name or calculation keyword for the element</td><td>string</td></tr></tbody></table>

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `obj_typ` → `ru_elem(i)%obtyp`; `obj_id` → `ru_elem(i)%obtypno`; `dlr` → `ru_elem(i)%dr_name`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_read_elements.f90#L71).
