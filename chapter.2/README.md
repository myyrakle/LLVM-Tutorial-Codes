Here is the complete code listing for our running example.  
Because this uses the LLVM libraries, we need to link them in.  
To do this, we use the llvm-config tool to inform our makefile/command line about which options to use:

```
# Compile
clang++ -g -O3 toy.cpp `llvm-config --cxxflags`
# Run
./a.out
```
