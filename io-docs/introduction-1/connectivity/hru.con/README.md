---
description: This file defines the connectivity of spatial objects.
---

# 'object'.con

| Field                  | Description                                             |   Type  |     Unit    | Default |     Range    |
| ---------------------- | ------------------------------------------------------- | :-----: | :---------: | :-----: | :----------: |
| [id](id.md)            | Unique ID of the object                                 | integer |     n/a     |   n/a   |      n/a     |
| [name](name.md)        | Name of the object                                      |  string |     n/a     |   n/a   |      n/a     |
| [gis\_id](gis_id.md)   | Object number in QSWAT+                                 | integer |     n/a     |   n/a   |      n/a     |
| [area](area.md)        | Area of the object                                      |   real  |      ha     |   n/a   |      n/a     |
| [lat](lat.md)          | Latitude of the object                                  |   real  | dec degrees |   n/a   |  -90.0-90.0  |
| [lon](long.md) | Longitude of the object (currently not used) | real | dec degrees | n/a | -180.0-180.0 |
| [elev](elev.md)        | Elevation of the object                                 |   real  |      m      |   n/a   |    0-7000    |
| [hru](hru.md)          | Pointer to the object data file                         | integer |     n/a     |   n/a   |      n/a     |
| [wst](wst.md) | Weather station name | string | n/a | n/a | n/a |
| [cst](cst.md)          | Currently not used                                      | integer |     n/a     |   n/a   |      n/a     |
| [ovfl](ovfl.md)        | Currently not used                                      | integer |     n/a     |   n/a   |      n/a     |
| [rule](rule.md)        | Name of the flow-control decision table in flo\_con.dtl that controls this object's outflow (null if none) |  string |     n/a     |   n/a   |      n/a     |
| [out\_tot](out_tot.md) | Total number of outgoing hydrographs | integer | n/a | n/a | 0-12 |
| [obj\_typ](obj_typ.md) | Type of the receiving object                            |  string |     n/a     |   n/a   |      n/a     |
| [obj\_id](obj_id.md)   | ID of the receiving object                              | integer |     n/a     |   n/a   |      n/a     |
| [hyd\_typ](hyd_typ.md) | Type of hydrograph that is sent to the receiving object |  string |     n/a     |   n/a   |      n/a     |
| [frac](frac.md)        | Fraction of hydrograph sent to the receiving object     |   real  |   fraction  |   n/a   |    0.0-1.0   |
