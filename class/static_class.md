好的，接下来我将继续补充文档中的静态类部分：

---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 静态类

静态类是一个特殊的类，它不能实例化，并且所有成员必须是静态的。静态类通常用于封装一些工具方法或常量，方便在整个程序中共享。

### 定义静态类

在 C# 中，使用 `static` 关键字来定义静态类。静态类与普通类的区别在于，它无法创建对象实例，并且类中的所有成员都必须是静态的。

```csharp
public static class MathUtils
{
    // 静态方法
    public static int Add(int a, int b)
    {
        return a + b;
    }

    // 静态字段
    public static double Pi = 3.14159;

    // 静态属性
    public static string Version { get; } = "1.0";
}
```

### 静态类的特点

1. **不能实例化**：静态类不能通过 `new` 关键字实例化。例如，`MathUtils mathUtils = new MathUtils();` 会引发编译错误。
   
2. **只能包含静态成员**：静态类的成员必须是静态的，包括方法、属性、字段等。你不能定义实例成员。

3. **适用于工具类和常量存储**：静态类通常用于存储与实例无关的常量或工具方法，方便在整个程序中访问。

4. **不能继承**：静态类不能继承其他类，也不能被其他类继承。

### 使用静态类

你可以直接通过类名来访问静态类的成员，而无需创建对象实例。

```csharp
class Program
{
    static void Main(string[] args)
    {
        // 直接通过类名调用静态方法
        int result = MathUtils.Add(5, 3);
        Console.WriteLine($"Result: {result}");

        // 访问静态字段和静态属性
        Console.WriteLine($"Pi: {MathUtils.Pi}");
        Console.WriteLine($"Version: {MathUtils.Version}");
    }
}
```

### 静态构造函数

静态类可以定义静态构造函数，这个构造函数在类的任何静态成员首次被访问时自动调用。静态构造函数用于初始化静态成员，或者执行一次性的设置操作。静态构造函数没有访问修饰符，并且不能接受参数。

```csharp
public static class Config
{
    public static string ConnectionString { get; private set; }

    // 静态构造函数
    static Config()
    {
        // 初始化静态字段
        ConnectionString = "Data Source=server;Initial Catalog=db;Integrated Security=True";
    }
}

class Program
{
    static void Main(string[] args)
    {
        // 访问静态类时，静态构造函数会自动执行
        Console.WriteLine(Config.ConnectionString);
    }
}
```

### 静态类的使用场景

静态类通常用于以下场景：

- **工具类**：提供一些公共的方法（如数学计算、字符串处理等），避免每次都创建类的实例。
  
- **常量存储**：存储常量值或配置数据，使这些值在整个应用程序中共享。

- **单例模式的实现**：虽然静态类本身就无法实例化，但可以用来实现单例模式（即确保某些类只有一个实例）。

### 静态类与普通类的比较

| 特性                | 静态类                      | 普通类                          |
|---------------------|-----------------------------|---------------------------------|
| 是否可以实例化      | 不能                        | 可以                           |
| 成员类型            | 只能是静态成员              | 可以有实例成员和静态成员        |
| 继承性              | 不能继承其他类，不能被继承   | 可以继承其他类                  |
| 构造函数            | 只能有静态构造函数           | 可以有实例构造函数和静态构造函数 |
| 使用场景            | 工具类、常量类等             | 一般业务类                      |

---