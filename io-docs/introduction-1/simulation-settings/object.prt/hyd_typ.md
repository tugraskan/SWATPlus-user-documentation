---
description: Type of hydrograph to print
---

# hyd\_typ

**Code reference:** `ob_out(ii)%hydtyp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L263)).

Mapped to `ob_out(i)%hydno` in [`object_read_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/object_read_output.f90#L78-L116) and dispatched daily in [`obj_output.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/obj_output.f90#L35-L165) (note that `solnut_ly` and `solnut_pr` do not write a header line when opened). The following hydrographs and object outputs can be printed:

| Hydrograph Code | Description                                 | Object type |
| --------------- | ------------------------------------------- | ----------- |
| tot             | Total flow                                  | all         |
| rhg             | Percolation                                 | hru, ru     |
| sur             | Surface runoff                              | hru, ru     |
| lat             | Lateral flow                                | hru, ru     |
| til             | Tiledrain flow                              | hru, ru     |
| sol\_water      | Soil moisture                               | hru         |
| solnut\_ly      | Soil nutrients (N and P) by layer           | hru         |
| solnut\_pr      | Soil nutrients (N and P) for entire profile | hru         |
| plant           | Plant status                                | hru         |
| cha\_fp         | Channel and floodplain water balance        | sdc         |
