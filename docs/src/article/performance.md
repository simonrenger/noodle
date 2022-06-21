# Performance

*Development performance*

 One of the most important factors for the game industry is the ability to perform quick iteration cycles and to be able to quickly prototype a feature [23, pp. 956–957] [20], [24]. Many interviewees have expressed the opinion that script hot reloading is a crucial feature they would expect from a VSL. It has been shown also in literature [23] that script hot reloading is a great feature, that supports quick iteration and rapid prototyping. Based on these observations, Noodle will support script hot reloading to empower users with quick prototyping.

*Runtime performance*

 When talking to any game programmer, they will most likely make a similar statement as many of the study participants, that memory is the number one bottleneck in games. Although, it greatly depends on the requirements of the game and how dramatic the runtime performance is influenced by the right memory access patterns or the right allocation strategies. Therefore, it is not surprising that most of the participants expressed their opinions on how memory management should work. The major conclusion is that in a VSL, we know from early on what kind of data we will handle since all inputs and outputs of all nodes are known at translation time, therefore the graph could either allocate a large chunk of memory and manage that like in [WebAssembly](https://www.fastly.com/blog/webassembly-memory-management-guide-for-c-rust-programmers) where “...opcodes accessing memory are not given addresses, but offsets relative to the beginning of a linear memory segment whose size is always known.” The memory model of Noodle will follow the same mentality and will at the beginning allocate the needed memory through a memory allocator interface that the user can modify, if needed. If memory needs to be accessed in a form of a pointer, Noodle will not be able to do anything with these pointers, so it will just pass them down to native functions that are able to understand them.

When it comes to a scripting language and a VSL, which is nothing else than a subcategory [1], [25], the execution method is important. Robert Nystrom states in both of his books “Crafting interpreters” and “Game programming patterns” [26, p. 17], [27, pp. 155–179] that a tree-walking interpreter, a form of an interpreter that traverses the graph by recursively calling the nodes, is slower than compiling the graph down to bytecode that is executed in a virtual machine (VM) or transpiled to a different source code [26, pp. 16–20], [28], [27, pp. 155–179] ,[23, pp. 52,954-958]. Based on these findings, Noodle will compile to bytecode with the intention that the user can compile a Noodle graph representation to C and compile to native code depending on their platform as a last shipping step (if providing a backend). This transpiling or compiling to native code has been mentioned in the interviews as an important feature. It can also be considered to allow the language to enable hot patching of the native generated code. This means that if something is wrong with the compiled C code, a content update of a bytecode compiled graph can be used to hot patch this part of the code.