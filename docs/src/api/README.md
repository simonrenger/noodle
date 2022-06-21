# Noodle API Specifications

Noodles API is written in the C programming language since C is considered as the lingua franca of programming languages [18]–[21]. To provide maximal portability from an API point of view, the header files of Noodle will be written in C99 and the implementation will be done in C11.

## Including

There are two ways to get the Noodle embedded into your program:

1. Link the statically build library or the dyanmically library.
2. You can include the noodle source code as part of your application.

However you choose to embedd noodle, you also want to add `src/include` to your include path to be able to include the `noodle.h` file.

Noodle depends only on the C standard library, so you don’t usually need to link to anything else. Be aware that this is a subject to change and maybe we offer a customization point to get ride of these dependencies as well.

If your program is in C++ but its linking to the noodle library compiled as C you need to include the following header file:

```c
#include "noodle.hpp"
```

## Initilization

> This will be added soon
