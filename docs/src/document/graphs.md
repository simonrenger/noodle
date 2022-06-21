# Graphs

```json
{
    "protocol": {
        "version": "0.0.1",
        "lang": "noodle"
    },
    "graphs": [ ],
    "editors": []
}
```

| Field  | Type          | Description                 |
| ------ | ------------- | --------------------------- |
| graphs | Array<Object> | An array of `graph` objects |

## Details `graphs object`

```json
{
    "protocol": {
        "version": "0.0.1",
        "lang": "noodle"
    },
        "graphs": [
            {
                "name": "Main",
                "graph": {
                    "nodes": [],
                    "connections": [],
                    "data": [],                    
                }
            }
        ],
    "editors": []
}
```

| Field | Type   | Description                 |
| ----- | ------ | --------------------------- |
| name  | string | name of the graph.          |
| graph | Object | Actual data used for the VM |

### Details `graph`

| Field       | Type                 | Description                                                  |
| ----------- | -------------------- | ------------------------------------------------------------ |
| nodes       | Array<Object>        | List of Nodes defining the graph.                            |
| connections | Array<Array<Object>> | List of connections used by the graph's nodes. If no connection is given the array is empty. |
| data        | Array<Object>        | List of data used by the graph's nodes. If no data is given the object is empty. |

### **Details: `node`**

```json
            {
                "name": "Number",
                "node":"123e4567-e89b-12d3-a456-426614174000",
                "id": 1
            }
```

| Field | Type          | Description            |
| ----- | ------------- | ---------------------- |
| name  | string        | Name of the Node       |
| id    | number/string | Unique ID of the node. |
| node  | string        | Unique ID of the node. |

### **Details: `connections`**

````json
"connections": [
            [],
            [],
            [
                {
                    "type": "output",
                    "name": "res",                    
                    "extern": "b",
                    "node": 5                
                }
            ],
    ]
````

| Field  | Type   | Description                                   |
| ------ | ------ | --------------------------------------------- |
| type   | string | Type of the connection: `input` or `output`   |
| name   | string | Name of the input\|output on the current node |
| extern | string | The name of the extern connector.             |
| node   | number | The id of the extern node.                    |

### **Details: `data`**

```json
"data": [
    {},
    {	"num":{
        	"type": "number",
	        "value": "1"
    	}
    }
    ]
```

The data object itself is structured in a way that the Connector name is the name of the object key.