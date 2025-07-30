# Shared Libraries

- Linux shared libraries are used to facilitate the sharing of library files by multiple computer programs.  
- **Static and dynamic** shared libraries <ins>differ in how they are used during the compilation and running of a program.</ins>

<br>

## Static Shared Libraries:
- During compilation, static shared libraries used by program source code are embedded into the program by the linking process.
- This makes the shared library part of the final, standalone executable program file.
- When the static shared library has been read and the program compiled, the static shared library is no longer needed.
- Later, when the program is run, the program uses the copy of the static library that the linker originally merged into the executable during compilation.

### Benefits:
- Applications have **no** external dependencies with their libraries at runtime.

### Challenges:
- It produces a larger final, standalone executable program file, which requires more memory to run.
- When multiple programs use an identical library, duplicate copies of that library will be in memory at the same time, consuming more memory.
- Applications must be recompiled to incorporate changes to their static shared libraries.

> [!NOTE]
> Static libraries usually follow a naming convention that adds the .a suffix to the end of each library name.

<br>

## Dynamic Shared Libraries:
- During complilation, dynamic shared libraries used by program source code are referenced using links to those libraries, in their existing locations.
- When the program is run, the program uses the dynamic links to the library files that it originally read at compilation time.
