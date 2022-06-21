# Types

These are the identifications of the supported data types. In its default configuration the VM understands:

- `number`  - a float 64 value (`double`)
- `boolean` -  `true` / `false` 
- `string` - Its basically a `const char*` & `uint32_t` size and `uint32_t` end of line flag and owned by the VM

```json
    "types": [
        {
            "name": "number",
            "compatible": []
        }
    ],
```

| Field      | Type          | Description                                                  |
| ---------- | ------------- | ------------------------------------------------------------ |
| name       | string        | Name of the type (lower letters)                             |
| compatible | Array<string> | List of names of types this type is compatible with. (Implicit castable) |