# Protocol

As mentioned above, Noodle runs on a protocol that gives an overview of what nodes are available and what types can the runtime understand. This indicates that Noodle can be either statically or more dynamically typed, depending on the needs of the dialect designer. The Noodle protocol can be generated via the API and will return either a protocol struct that can be used via the C interface or a JSON representation that can be used otherwise in tools or in the WebSocket API. 

Besides the Noodle protocol that describes the language, there is the *noodle file* or *noodle document –* the script file. One can see the protocol like a header file in C or C++ and a noodle file as the source file. The noodle document describes the current file the VM is processing. As mentioned above, each noodle file may contain subgraphs (internal modules) or if enabled, external modules. In principle, every noodle document contains three regions: 

***Protocol*** – this region describes the meta data of the current language dialect. The VM will check this region and verify that the name of the dialect, as well as the version, are matching. If not, the file cannot be passed. Migration can be implemented with this approach.

***Graph*** – this region describes the actual data of the graph, which includes the modules, nodes, connections, and the data. 

***Editor*** – implementation defined region that can be used to define editor specific data such as position of nodes, etc. This region is not used by the VM in any way.

The *graph* region is the only region where the VM interpreter needs to understand the data of the file, while the *protocol* region is there to make sure that the noodle file matches this dialect.
