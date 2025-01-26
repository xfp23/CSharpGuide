
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---


# 函数

## 函数的基本声明与使用与 C/C++ 一致，这里不过多赘述，只介绍新特性

### ref 和 out 关键字

- 由于 C# 没有指针这一概念，所以 `ref` 关键字的作用类似于 C/C++ 中将地址传递给函数，使得函数能够直接修改变量的值。

- 把未赋值的变量传递给 `ref` 关键字是非法的，而 `out` 可以传递未初始化的变量。

- `out` 和 `ref` 的主要区别是：`out` 会丢弃原有的变量值，而 `ref` 需要在传递之前给变量赋值。

#### 示例：

```c#
using System;

class Program
{
    static void Main()
    {
        int x = 10;
        int resultRef;
        int resultOut;

        // 使用 ref
        AddFiveRef(ref x, out resultRef);
        Console.WriteLine("Result using ref: " + resultRef);

        // 使用 out
        AddFiveOut(0, out resultOut);
        Console.WriteLine("Result using out: " + resultOut);
    }

    static void AddFiveRef(ref int num, out int result)
    {
        num += 5; // 直接修改 ref 参数
        result = num; // 修改 out 参数
    }

    static void AddFiveOut(int num, out int result)
    {
        result = num + 5; // 直接初始化 out 参数
    }
}
```

---