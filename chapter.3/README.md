[한국어](./KOR.md)

Here is the complete code listing for our running example, enhanced with the LLVM code generator.  
Because this uses the LLVM libraries, we need to link them in.  
To do this, we use the llvm-config tool to inform our makefile/command line about which options to use:

```
# Compile
clang++ -g -O3 main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core` -o toy
# Run
./toy
```

Here is the code:  
[Code](./main.cpp)
