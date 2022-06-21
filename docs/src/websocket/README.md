# Language Server API

The Language Server API provides a WebSocket API the end user can connect to. The WebSocket API allows a bidirectional communication which can be seen as a favourable model over a REST API.

## Client Requests

The Language Server (LS) will operate on a specific port (specified in the configuration of the server) and allows N clients to connect. When a client connected the client has the possibility to request certain information from the Language Server:

| Request             | Content Type | Description                                                  |
| ------------------- | ------------ | ------------------------------------------------------------ |
| `/request_protocol` | text/json    | This will return the language protocol (Noodle Language Specification) |

## Client Events

The Client can send the following events to the LS:

| Client Events       | Content Type | Description                                                  |
| ------------------- | ------------ | ------------------------------------------------------------ |
| `/document_changed` | text/json    | This tells the server that the document has changed. The body contains the changed document. The reaction of this message is implementation defined. |

## Server Events

The LS can update the client with:

| LS Update           | Content Type | Description                                                  |
| ------------------- | ------------ | ------------------------------------------------------------ |
| `/protocol_changed` | text/json    | This tells the client the protocol has changed. The new protocol will be in the body.  (Noodle Language Specification) |
| `/error`            | text/json    | This will return a error object that describes in its `type` field what kind of error and the error message can be accessed in the `message.` |
| `/runs`             | text/json    | **Optional**.  It existences is implementation defined. This can be used to signal the client that the X files are in simulations. Could be used to implement hot reload / live changes together with `/document_changed`. |



## Example Communication

The user changes a graph and sends `/document_changed` to the server the server will apply the changes to the VM. The server will return the validation results via `/error` if there has been a error otherwiese nothing will be send to the user.
