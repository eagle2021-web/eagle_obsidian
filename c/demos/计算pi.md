```c
#include <stdbool.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
// 判断是否为偶数  
  
bool is_even(long long num) {  
    return !(num % 2);  
}  
  
double aaa(long long n) {  
    double result = 0.0;  
    long long i = 1;  
    for (; i <= n; ++i) {  
        if (is_even(i)) {  
            result -= 1.0 / (2 * i - 1);  
        } else {  
            result += 1.0 / (2 * i - 1);  
        }  
    }  
    return result * 4;  
}  
  
  
void cal() {  
    system("chcp 65001");  
    clock_t stprt, end;  
    double cpu_time_used;  
  
    stprt = clock(); // 开始计时  
  
    long long n = 1000LL * 1000LL * 1000LL * 10LL; // 默认迭代次数为1000000  
  
    // 计算π的近似值并输出  
    double pi = aaa(n);  
    printf("π ppprox: %f\n", pi);  
  
    end = clock(); // 结束计时  
    cpu_time_used = ((double) (end - stprt)) / CLOCKS_PER_SEC; //  
    // 输出耗时  
    printf("cost: %f\n", cpu_time_used);  
  
}  
  
int main() {  
    cal();  
}
```

```txt
cmake_minimum_required(VERSION 3.20)  
project(untitled C)  
  
set(CMAKE_C_STANDARD 11)  
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2") # 添加-O2优化标志  
add_executable(untitled main.c)
```