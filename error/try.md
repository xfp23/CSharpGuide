
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---
---

# 异常捕获

在 C# 中，异常处理使用 `try`、`catch` 和 `finally` 块。这三个关键字需要连续使用，帮助捕获程序中可能出现的错误，并采取适当的措施来处理这些错误，避免程序崩溃。

### 异常处理语法

```c#
try
{
    // 可能抛出异常的代码
}
catch (ExceptionType ex)
{
    // 捕获并处理异常
}
finally
{
    // 无论是否发生异常，最终都会执行的代码
}
```

### 常见异常

1. **ArgumentException**  
   当向方法提供了无效的参数时抛出。

2. **ArgumentNullException**  
   当传递的参数为 `null`，但方法不允许时抛出。

3. **ArgumentOutOfRangeException**  
   当传递的参数值超出允许的范围时抛出。

4. **NullReferenceException**  
   当试图访问未初始化（为 `null`）的对象时抛出。

5. **InvalidOperationException**  
   当对象当前状态不适合所请求的操作时抛出。

6. **FormatException**  
   当格式不正确时抛出。例如，尝试将字符串转换为数字，但格式不符。

7. **OverflowException**  
   当算术运算导致溢出（超出类型表示范围）时抛出。

8. **DivideByZeroException**  
   当尝试除以零时抛出。

9. **StackOverflowException**  
   当堆栈溢出时抛出，通常发生在无限递归的情况下。

10. **OutOfMemoryException**  
    当系统内存不足，无法分配对象时抛出。

11. **FileNotFoundException**  
    当试图访问不存在的文件时抛出。

12. **IOException**  
    当发生 I/O 操作错误时抛出，通常是多个 I/O 异常的基类。

13. **UnauthorizedAccessException**  
    当尝试访问未经授权的资源时抛出。

14. **KeyNotFoundException**  
    当试图通过键访问集合中不存在的键时抛出。

15. **NotSupportedException**  
    当方法或操作不被支持时抛出。

16. **TimeoutException**  
    当操作超时时抛出。

17. **TaskCanceledException**  
    当任务被取消时抛出。

18. **OperationCanceledException**  
    表示某操作被取消，通常与 `CancellationToken` 一起使用。

19. **ConcurrencyException**  
    当检测到并发冲突时抛出，通常发生在数据库相关操作中。

### 示例

```c#
using System;

class Program
{
    static void Main()
    {
        try
        {
            int x = 5, y = 0;
            int result = x / y;  // 此处将抛出除零异常

        }
        catch (DivideByZeroException ex)
        {
            Console.WriteLine("发生异常：除数不能为零!");
            Console.WriteLine("异常详情: " + ex.Message);
        }
        catch (Exception ex)
        {
            Console.WriteLine("发生其他异常: " + ex.Message);
        }
        finally
        {
            Console.WriteLine("执行完毕，无论是否发生异常");
        }
    }
}
```

### 异常处理关键点

- **`catch` 块**: 可以捕获特定类型的异常，如 `DivideByZeroException`、`NullReferenceException` 等，确保异常得到正确处理。
- **`finally` 块**: 用于确保即使发生异常，资源也能被正确释放。例如，关闭文件流、数据库连接等操作。
- **多个 `catch` 块**: 可以根据不同类型的异常，使用多个 `catch` 块进行分别处理。通常从最具体的异常类型开始捕获。
- **通用异常 `Exception`**: 最后的 `catch` 块通常用来捕获所有未被前面捕获的异常。
