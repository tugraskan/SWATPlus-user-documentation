---
description: Type of hydrograph to print
---

# hyd\_typ

**Code reference:** `ob_out(ii)%hydtyp` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L260)).

The following hydrographs can be printed:

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
| cha\_fp         | Channel and floodplain water balance        | hru         |
