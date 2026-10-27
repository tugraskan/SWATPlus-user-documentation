---
description: Number of columns to read for list of elements in the Routing Unit
---

# elem\_tot

**Code reference:** `nspu` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_read_elements.f90#L18)).

If each element in the Routing Unit is listed individually, the number of columns to read will equal the number of elements in the Routing Unit. However, if there are several elements with consecutive numbers in a Routing Unit, they can be listed by specifying the first one in one column and the last one with a hyphen in front of it in the next column.
