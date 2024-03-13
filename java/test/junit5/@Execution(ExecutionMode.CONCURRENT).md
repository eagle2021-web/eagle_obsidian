```java
package com.eagle;  
  
import org.junit.jupiter.api.Test;  
import org.junit.jupiter.api.TestInstance;  
import org.junit.jupiter.api.TestInstance.Lifecycle;  
import org.junit.jupiter.api.extension.ExtendWith;  
import org.junit.jupiter.api.parallel.Execution;  
import org.junit.jupiter.api.parallel.ExecutionMode;  
  
@TestInstance(Lifecycle.PER_CLASS)  
@Execution(ExecutionMode.CONCURRENT)  
public class ConcurrentExecutionDemo {  
  
    @Test  
    public void testMethodOne() {  
        System.out.println(System.currentTimeMillis());  
        System.out.println("Test method one, Thread: " + Thread.currentThread().getName());  
        // 模拟测试逻辑  
        try {  
            Thread.sleep(10000); // 暂停1秒钟模拟测试  
        } catch (InterruptedException e) {  
            Thread.currentThread().interrupt();  
        }  
    }  
  
    @Test  
    public void testMethodTwo() {  
        System.out.println(System.currentTimeMillis());  
        System.out.println("Test method two, Thread: " + Thread.currentThread().getName());  
        // 模拟测试逻辑  
        try {  
            Thread.sleep(10000); // 暂停1秒钟模拟测试  
        } catch (InterruptedException e) {  
            Thread.currentThread().interrupt();  
        }  
    }  
}
```


src/test/resources/junit-platform.properties

```properties
junit.jupiter.execution.parallel.enabled = true  
junit.jupiter.execution.parallel.mode.default = concurrent
```


```xml
<dependency>  
    <groupId>org.junit.jupiter</groupId>  
    <artifactId>junit-jupiter-api</artifactId>  
    <version>5.10.1</version>  
    <scope>test</scope>  
</dependency>
```

```log
1710337732861
1710337732861
Test method two, Thread: ForkJoinPool-1-worker-25
Test method one, Thread: ForkJoinPool-1-worker-18
```