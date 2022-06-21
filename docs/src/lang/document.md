# Document

Can be used a "untitled" document in a *VSE/VPE* such as in our example VS Code Extension Editor.

```json
    "document": {
        "protocol": {
            "version": "0.0.1",
            "lang": "noodle"
        },
        "graphs":[],
        "editors": []
    },
```

| Field    | Type          | Description                                                  |
| -------- | ------------- | ------------------------------------------------------------ |
| protocol | Object        | Contains the description of the protocol being use. Can be used to validate if the current file matches the currently used VM or Language file. Should be the same as in the top level protocol |
| graphs   | Array<Object> | Defines an array of Graph Elements that represent the actual data used by the VM |
| editors  | Array<Object> | Implementation defined by the Editor. This can be data used by the editor. The VM will ignore anything in this section. The index of a entry here needs to be aligned with the Graphs. |

For more information on the Document and how the graphs are structured please check later `Document Specification`.