Here is the complete code listing for our running example, enhanced with the support for user-defined operators. 
To build this example, use:

```
# Compile
clang++ -g main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# Run
./toy
```

On some platforms, you will need to specify -rdynamic or -Wl,–export-dynamic when linking. 
This ensures that symbols defined in the main executable are exported to the dynamic linker and so are available for symbol resolution at run time. This is not needed if you compile your support code into a shared library, although doing that will cause problems on Windows.

Here is the code:  
[Code](./main.cpp)
