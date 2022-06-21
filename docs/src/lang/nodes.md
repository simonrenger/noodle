# Nodes

Bare bone description of the nodes. This can be used by a *VSE/VEP* to parse the `.graph` fields. All graphs are composed out of these nodes.

```json
 {
 "name": "Number",
 "uuid": "123e4567-e89b-12d3-a456-426614174000",
 "input": [],
 "output": []
},
```

| Field | Type          | Description                   |
| ----- | ------------- | ----------------------------- |
| name  | string        | Name of node                  |
| uuid  | string        | Universally Unique Identifier |
| input | Array<Object> | List of Inputs                |

## **Details: `input/output`**

```json
{
"name": "num",
"pretty_name": "Number",
"type": "number",
"control": {},
"read_only": false,
"default_value": null,
"ref": false
}
```

| Field         | Type    | Description                                                  |
| ------------- | ------- | ------------------------------------------------------------ |
| name          | string  | Name of Input/Output                                         |
| pretty_name   | string  | Display Name                                                 |
| type          | string  | Valid type name of `.types` array                            |
| control       | object  | Describes the Input/Outputs control: e.g. Input Text box *(Just a suggestion)* |
| read_only     | boolean | Is this input/output a read only type? *(subject to change: e.g. const)* |
| default_value | any     | Default Value: `boolean|string|number`                       |
| ref           | boolean | Is this value a reference *(subject to change)*              |

> Reference type is only supported if the VM settings allow this. Also `read_only` might be implcit and one needs to specifically state that a input/output can be written to. This will be subject to change and only avalilbe for reference types since all wires are in general const and not mutable.



## Control Specifications

Can be ignored by the editor since the editor is implementation defined. This is just a method for the VM to provide suggestions or extra information.

### **General Overview**

```json
{
    "type": "select",
    "items": [
        "a","b"
    ],
    "options": [
        1,2
    ]
}
```

| Field   | Type       | Description                                                  |
| ------- | ---------- | ------------------------------------------------------------ |
| type    | string     | Type name of the control. The VM comes with build in: `number`,`text`,`checkbox`,`select`,`color`,`vec2-4`,`mat4` |
| items   | Array<any> | Implementation defined                                       |
| options | Array<any> | Implementation defined                                       |