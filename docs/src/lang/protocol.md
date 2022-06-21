# Protocol

Contains the description of the protocol being use. Can be used to validate if the current file matches the currently used VM or Language file. Every VM can typicaly only handle one protocol at the same time. 

```json
{
    "protocol": {
        "version": "0.0.1",
        "lang": "noodle"
    },
    // ...
}
```

| Field   | Type   | Description                                                  |
| ------- | ------ | ------------------------------------------------------------ |
| version | string | Version of the language that is used in the `graph` section. This is used by the VM to validate the VM's Version with this files version. |
| lang    | string | Identifier for the language that is used in the `graph` section. This is used by the VM to checked if the VM language is not equal the VM will cause a error. |