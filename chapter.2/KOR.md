다음은 실행 예제의 전체 코드 목록입니다.  
이건 LLVM 라이브러리를 쓰기 때문에, 직접 링크할 필요가 있습니다.  
이를 위해 llvm-config 도구를 사용해 makefile/명령행에 사용할 옵션을 알려줍니다.

```
# 컴파일
clang++ -g -O3 main.cpp `llvm-config --cxxflags`
# 실행
./a.out
```

코드는 여기 있습니다.  
[Code](./main.cpp)
