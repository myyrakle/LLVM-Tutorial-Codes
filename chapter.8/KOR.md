# 다 모아서 컴파일하기

잘 작동할까요? 일단 돌려봅시다.  

우린 여전히 코드를 컴파일할 필요가 있지만, llvm-config로 보낼 인자가 이전 챕터와는 다릅니다.
 
 ```
$ clang++ -g -O3 main.cpp `llvm-config --cxxflags --ldflags --system-libs --libs all` -o toy
```

이제 실행해봅시다. 그리고 간단한 average 함수를 정의하는 겁니다.  
다 됐으면 컨트롤+D를 누릅니다.

```
$ ./toy
ready> def average(x y) (x + y) * 0.5;
^D
Wrote output.o
```

그럼 이제 오브젝트 파일이 나왔을 겁니다!   
이걸 테스트하려면, 간단한 프로그램을 작성해서 출력물에 링크를 하면 됩니다.

다음은 그 소스코드입니다.  

```
#include <iostream>

extern "C" {
    double average(double, double);
}

int main() {
    std::cout << "average of 3.0 and 4.0: " << average(3.0, 4.0) << std::endl;
}
```
  
이 프로그램을 output.o와 링크해서 그 결과가 예상대로 나오는지 확인해봅시다.
```
$ clang++ test.cpp output.o -o test
$ ./test
average of 3.0 and 4.0: 3.5
```

코드:  
[Code](./main.cpp)
