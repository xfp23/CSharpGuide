
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# params 关键字

- `params` 关键字允许你给函数指定一个特殊的参数（只能有一个且是最后一个参数），它用于接收一个可变长度的参数数组。这使得调用函数时不需要显式地指定每一个参数，提供了更加灵活的调用方式。

## 示例：

```c#
using System;

class Program
{
    static void Main()
    {
        // 使用 params
        Console.WriteLine(Sum(1, 2, 3, 4, 5));
        Console.WriteLine(Sum(10, 20));
    }

    static int Sum(params int[] numbers)
    {
        int sum = 0;
        foreach (int number in numbers)
        {
            sum += number;
        }
        return sum;
    }
}
```