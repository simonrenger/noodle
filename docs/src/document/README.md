# Document Specification

A Noodle file is a file with the file ending: `.noodle` and follows the same structure as defined in the Noodle Language Specifications.

### **General Overview**

```json
{
    "protocol": {},
    "graphs": [],
    "editors": []
}
```

| Field    | Type          | Description                                                  |
| -------- | ------------- | ------------------------------------------------------------ |
| protocol | Object        | Contains the description of the protocol being use. Can be used to validate if the current file matches the currently used VM or Language file. |
| graphs   | Array<Object> | Defines an array of Graph Elements that represent the actual data used by the VM |
| editors  | Array<Object> | Implementation defined by the Editor. This can be data used by the editor. The VM will ignore anything in this section. The index of a entry here needs to be aligned with the Graphs |