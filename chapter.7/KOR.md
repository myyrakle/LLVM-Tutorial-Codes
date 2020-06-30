다음은 가변 변수와 var/in 지원이 추가된 실행 예제의 전체 코드 목록입니다.
  
빌드하려면, 이렇게 합니다.

```
# 컴파일
clang++ -g main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# 실행
./toy
```

코드는 여기로  
[Code](./main.cpp)
