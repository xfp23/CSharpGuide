
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 委托 (delegate)

### 委托的基本思想

委托在 C# 中类似于 C/C++ 中的函数指针，但 C# 没有指针的概念，因此使用委托（`delegate`）来实现类似的功能。委托允许将方法作为参数传递，或者将多个方法组合在一起执行。

### 1. 定义委托类型

首先，定义一个委托类型时，需要指定它的返回类型和接受的参数类型。

```c#
// 关键字 delegate 函数返回类型 委托类型名 接收的参数
delegate double MyDelegate(double param1, double param2);
```

### 2. 声明委托变量

声明委托类型的变量与普通变量的声明类似：

```c#
MyDelegate name; // 委托类型变量
```

### 3. 使用委托

使用委托时，首先需要定义一个方法，然后将该方法与委托关联。委托变量可以像调用普通方法一样调用。

#### 示例：

```c#
using System;

class Program
{
    // 定义委托
    delegate double MyDelegate(double param1, double param2);

    static void Main()
    {
        // 声明委托变量
        MyDelegate name;

        // 定义一个要委托的方法
        double Multiply(double param1, double param2) => param1 * param2;

        // 将委托指向 Multiply 方法
        name = new MyDelegate(Multiply);

        // 使用委托变量调用方法
        double result = name(10, 20);

        // 输出结果
        Console.WriteLine("Multiplication result: " + result);
    }
}
```

### 委托的工作流程

1. **声明委托类型**：用 `delegate` 关键字定义一个委托类型，指定返回类型和参数类型。
2. **声明委托变量**：声明一个该类型的委托变量。
3. **绑定方法**：将一个实际方法赋值给委托变量。
4. **调用委托**：通过委托变量调用方法，类似调用普通方法。

委托允许你在运行时动态地选择方法，或者组合多个方法来实现某些特定的功能。