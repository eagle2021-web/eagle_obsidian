```java
package com.eagle;  
  
import org.junit.jupiter.api.Test;  
import org.junit.jupiter.api.parallel.Execution;  
import org.junit.jupiter.api.parallel.ExecutionMode;  
import org.junit.jupiter.api.parallel.ResourceLock;  
  
@Execution(ExecutionMode.CONCURRENT)  
public class ResourceLockExample {  
  
    @Test  
    @ResourceLock("SHARED_RESOURCE")  
    void testMethodOne() throws InterruptedException {  
        // 访问同一共享资源  
        System.out.println(System.currentTimeMillis());  
        Thread.sleep(3000);  
    }  
  
    @Test  
    @ResourceLock("SHARED_RESOURCE")  
    void testMethodTwo() throws InterruptedException {  
        // 访问同一共享资源  
        System.out.println(System.currentTimeMillis());  
        Thread.sleep(3000);  
  
    }  
  
    @Test  
    void testMethodThree() throws InterruptedException {  
        // 该方法可以与其他方法并行执行，因为它没有使用@ResourceLock  
        System.out.println(System.currentTimeMillis());  
        Thread.sleep(3000);  
    }  
}

```

`@ResourceLock`是JUnit Jupiter提供的一个注解，用于声明测试之间共享资源的锁。这个注解可以帮助解决在并行测试执行时可能出现的资源竞争问题，确保当多个测试方法访问相同的资源时，它们不会相互干扰，从而提高测试的可靠性和稳定性。

### 使用`@ResourceLock`的场景

- **共享资源**：当测试需要访问共享资源（如文件系统、数据库连接或任何外部系统）时，使用`@ResourceLock`可以防止并发访问导致的问题。
- **静态变量**：在测试类中使用静态变量时，不同的测试方法可能会修改这些变量的值，导致测试之间的相互影响。通过`@ResourceLock`，可以避免这种情况。
- **环境设置**：如果多个测试方法需要对环境进行修改（如更改系统属性），使用`@ResourceLock`可以确保这些操作不会因并行执行而冲突。

### 使用方法

`@ResourceLock`注解可以应用于测试方法或测试类。它需要一个值来标识被锁定的资源。所有使用相同资源标识符的测试将会顺序执行，而不是并行执行。

在这个示例中，`testMethodOne`和`testMethodTwo`访问了相同的共享资源，因此通过使用相同的资源锁`"SHARED_RESOURCE"`，我们确保了这两个方法不会并行执行。`testMethodThree`没有使用`@ResourceLock`，因此它可以与其他不冲突的测试方法并行执行。

### 注意事项

- **锁的范围**：`@ResourceLock`提供的是一种逻辑锁，依赖于JUnit Jupiter的执行引擎来尊重这一约定。它不能用于跨JVM的锁定或在非JUnit环境中强制执行。
- **锁的粒度**：合理地定义资源锁的粒度对于测试执行的性能和并发度至关重要。太粗的锁粒度会降低并发度，而太细可能不足以防止冲突。
- **版本要求**：`@ResourceLock`及相关的并行测试功能要求JUnit Jupiter的相应版本支持，因此确保你的项目依赖中包含了正确的JUnit版本。