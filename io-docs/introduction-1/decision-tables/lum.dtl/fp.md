---
description: File pointer
---

# fp

**Code reference:** `dtbl_lum(i)%act(iac)%file_pointer` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/conditional_module.f90#L25)).

The file pointer is only needed for certain actions. The file that is referenced by the file pointer depends on the action. The table below lists the actions that use the file pointer and which file it points to.

| **Action**    | **File referenced by file pointer**                                                                                      |
| ------------- | ------------------------------------------------------------------------------------------------------------------------ |
| harvest       | [harv.ops](../../management-practices/harv.ops/) ([name](../../management-practices/harv.ops/name_harvops.md))           |
| harvest\_kill | [harv.ops](../../management-practices/harv.ops/) ([name](../../management-practices/harv.ops/name_harvops.md))           |
| pest\_apply   | [chem\_app.ops](../../management-practices/chem_app.ops/) ([name](../../management-practices/chem_app.ops/name_chem.md)) |
| fertilize     | [chem\_app.ops](../../management-practices/chem_app.ops/) ([name](../../management-practices/chem_app.ops/name_chem.md)) |
