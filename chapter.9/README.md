Here is the complete code listing for our running example, enhanced with debug information.  
To build this example, use:

```
# Compile
clang++ -g main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# Run
./toy
```

Here is the code:  
[Code](./main.cpp)
