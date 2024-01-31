```cpp
#include <iostream>  
#include <chrono>  
#include <cstdlib>  
// 判断是否为偶数  
bool even() {  
    return false;  
}  
bool isEven(int v) {  
    return v % 2 == 0;  
}  
  
double piApproximation(int n) {  
    double result = 0.0;  
    for (int i = 1; i <= n; ++i) {  
        result += isEven(i) ? -1.0 / (2 * i - 1) : 1.0 / (2 * i - 1);  
    }  
    return result * 4.0;  
}  
  
int main(int argc, char* argv[]) {  
    auto startTime = std::chrono::high_resolution_clock::now();  
    double pi = piApproximation(n);  
    auto endTime = std::chrono::high_resolution_clock::now();  
  
    std::chrono::duration<double> diff = endTime - startTime;  
  
    std::cout.precision(25);  
    std::cout << pi << " cost: " << diff.count() << " seconds";  
  
    std::scientific(std::cout);  
    std::cout <<" num = "<<  double(n) << std::endl;  
    return 0;  
}
```

```txt
cmake_minimum_required(VERSION 3.20)  
project(untitled1)  
#set(CMAKE_CXX_FLAGS_DEBUG "-g")  
#set(CMAKE_CXX_FLAGS_RELEASE "-O2 -DNDEBUG")  
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2")  
set(CMAKE_CXX_STANDARD 20)  
  
add_executable(untitled1 main.cpp)
```