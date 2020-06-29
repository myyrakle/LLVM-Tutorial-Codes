다음은 사용자 정의 연산자 지원이 추가된 실행 예제의 전체 코드 목록입니다.  
아래와 같이 사용할 수 있습니다.

```
# 컴파일
clang++ -g main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs core mcjit native` -O3 -o toy
# 실행
./toy
```

일부 플랫폼에선, 링크를 할 때 -rdynamic나 -Wl, –export-dynamic를 지정해줄 필요가 있습니다.
This ensures that symbols defined in the main
 executable are exported to the dynamic linker
 and so are available for symbol resolution
 at run time. 
이건 메인 실행파일에서 정의된 심볼들이 동적 링커로 배출(export)해서, 심볼 해결이 런타임에도 가능하게 해줍니다.

This is not needed if you 
compile your support code into a shared 
library, although doing that will cause 
problems on Windows.


코드는 여기로:  
[Code](./main.cpp)
