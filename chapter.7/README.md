Here is the complete code listing for our running example, enhanced with mutable variables and var/in support.  
To build this example, use:

```
# Compile
clang++ -g toy.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# Run
./toy
```

Here is the code:  
[Code](./main.cpp)
