다음은 LLVM JIT과 옵티마이저로 발전한 실행 예제의 코드 목록입니다.  
이 예제를 빌드하려면, 아래와 같이 하면 됩니다.

```
# Compile
clang++ -g main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# Run
./toy
```

리눅스에서 컴파일한다면 "-rdynamic" 옵션을 추가로 줘야합니다.  
외부 함수들이 런타임에 잘 해결되는지도 확실히 해야하고요
  
코드는 여기에 있어요.  
[Code](./main.cpp)
