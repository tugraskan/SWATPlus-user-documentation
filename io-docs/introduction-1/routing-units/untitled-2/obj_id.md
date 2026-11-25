---
description: Object ID of the element
---

# obj\_id

**Code reference:** `ru_elem(i)%obtypno` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L494)).

The object ID of the element is a foreign key referencing [id](../../connectivity/hru.con/id.md) of the object in its corresponding [connect](../../connectivity/hru.con/) file (for the object type given in [obj\_typ](obj_typ.md)).

During element setup in [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L144-L162), SWAT+ maps `obtypno` to the global object index `ru_elem(ii)%obj` using the type's starting offset (`sp_ob1%<typ> + obtypno - 1`).
