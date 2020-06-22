Here is the complete code listing for our running example, enhanced with the LLVM JIT and optimizer.  
To build this example, use:

```
# Compile
clang++ -g toy.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# Run
./toy
```

If you are compiling this on Linux, make sure to add the “-rdynamic” option as well.  
This makes sure that the external functions are resolved properly at runtime.  
  
Here is the code:  
[Code](./main.cpp)
