다음은 if/then/else와 표현식이 추가된 우리 실행예제의 전체 코드 목록입니다.  
빌드는 다음과 같이 할 수 있어요.

```
# 컴파일
clang++ -g main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# 실행
./toy
```

코드는 여기로  
[Code](./main.cpp)
