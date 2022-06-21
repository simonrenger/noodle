# Language Specification

The Noodle Language Specification defines the language dialect. A VM can usually only handle one dialect at the same time. The specification be retierved from the VM's API. The VM will provide a JSON document containing the language specification or a language specification structure in C. 

## Language Specification

The JSON representation of the language dialect (noodle) can be used to communicate with the VM either via the WebSocekt API or via the general API. The difference lays that the general API structures are C structs modeled in a similar manner than the JSON structures. This allows that any extern editor that can parse a json file can understand the language dialect  and parse a `.noodle` file. This is demonstarted in the VS Code Extension.



## How will the JSON  be generated?

The JSON is generated via the API as mentioned above and reflects all registered nodes and data types to the VM. Also it will contain extra information about the current dialect. The C API can also read the protocol and configure itself based on this. **Note** that in this case native functions still need to be bound! 

## General JSON structure

```json
{
    "protocol": {
    },
    "document": {
    },
    "types": [
    ],
    "nodes": [
    ]
}
```

| Field    | Type          | Description                                                  |
| -------- | ------------- | ------------------------------------------------------------ |
| protocol | Object        | Contains the description of the protocol being use. Can be used to validate if the current file matches the currently used VM or Language file. |
| document | Object        | Defines the document structure.                              |
| types    | Array<Object> | List of possible types a node can refer to and the VM knows about. Will always contain the basic primitive types. |
| nodes    | Array<Object> | List of nodes the language understands                       |
