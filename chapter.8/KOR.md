# 다 모아서 컴파일하기

Does it work? 
잘 작동하나요?
Let’s give it a try. 


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

We have an object file! To test it, let’s write a simple program and link it with our output. 
Here’s the source code:

```
#include <iostream>

extern "C" {
    double average(double, double);
}

int main() {
    std::cout << "average of 3.0 and 4.0: " << average(3.0, 4.0) << std::endl;
}
```

We link our program to output.o and check the result is what we expected:

```
$ clang++ test.cpp output.o -o test
$ ./test
average of 3.0 and 4.0: 3.5
```

[Code](./main.cpp)
