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
- There is no merge of the shared libraries into the final, standalone executable file.

### Benefits:
- **Produces a smaller final, standalone executable program file, which consumes less memory at runtime.**
- The libraries **can be changed without recompiling the app.**

### Challenges:
- Apps load times can take longer while dynamic shared libraries are loaded into memory.
- Missing or corrupted dynamic libraries can cause the executable program file to fail.
- Multiple programs might require different versions of the same shared library at the same time.

> [!NOTE]
> File-naming convention for library files can help avoid challenges caused by multiple programs
> requiring different version of the same shared library at the same time.
> soname is composed of three parts:
* prefix: example **lib**
* designator **so**: stands for shared object
* suffix: version number
```
/usr/lib64/libpthread.so.0
```
<br>

- **libpthread** shared library name, usually prefixed with lib  
- **so** indicates this is a shared object  
- **0** Version number of the shared library