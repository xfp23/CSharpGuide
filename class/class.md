好的，我可以帮你完成这个 C# 编程指南的文档。下面是文档的继续部分，我会根据你给的内容和格式进行编写：

---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 类

类的内容与 C++ 相似，但 C# 中有一些特性，如属性、自动属性、访问修饰符等，允许更简单的代码实现。

## 定义类

在 C# 中，类的定义使用 `class` 关键字。类的构造方法与 C++ 中的构造函数类似，但不需要指定返回类型。

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // 构造方法
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```

## 属性 (Properties)

C# 引入了属性，作为对字段的封装方式。属性通过 `get` 和 `set` 方法来获取和设置字段值。自动属性是 C# 的一项便捷功能，不需要手动编写 `get` 和 `set` 方法，编译器会为我们自动生成。

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // 无需显式字段定义，自动属性会自动为你创建一个私有字段
    public string Address { get; set; }
}
```

你也可以自定义 `get` 和 `set` 方法，来实现更复杂的逻辑。

```csharp
public class Person
{
    private int age;
    public int Age
    {
        get { return age; }
        set 
        { 
            if (value >= 0)
                age = value;
            else
                throw new ArgumentException("Age cannot be negative");
        }
    }
}
```

## 构造函数 (Constructors)

C# 中的构造函数与 C++ 类似，但不需要指定返回类型。你可以创建多个构造函数来实现不同的初始化方式（这称为构造函数重载）。

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // 默认构造函数
    public Person()
    {
        Name = "Unknown";
        Age = 0;
    }

    // 带参数的构造函数
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```

## 继承 (Inheritance)

C# 支持面向对象编程中的继承。一个类可以从另一个类派生，继承其成员和方法，并可以覆盖（`override`）或隐藏（`new`）父类的方法。

```csharp
public class Employee : Person
{
    public string Position { get; set; }

    // 构造函数
    public Employee(string name, int age, string position)
        : base(name, age)  // 调用父类的构造函数
    {
        Position = position;
    }

    // 方法重写
    public override string ToString()
    {
        return $"{Name}, {Age} years old, {Position}";
    }
}
```

## 访问修饰符 (Access Modifiers)

C# 提供了几个访问修饰符来控制类成员的可见性：

- `public`：成员可以在任何地方访问。
- `private`：成员只能在类的内部访问。
- `protected`：成员只能在类及其派生类中访问。
- `internal`：成员只能在同一程序集内访问。
- `protected internal`：成员可以在同一程序集或派生类中访问。

```csharp
public class Person
{
    public string Name { get; set; }
    private int age;  // 只能在此类内部访问

    public Person(string name, int age)
    {
        Name = name;
        this.age = age;
    }

    // 公有方法来访问私有字段
    public int GetAge()
    {
        return age;
    }
}
```

---

## 方法

### 定义方法

C# 中的方法可以定义返回类型、参数和修饰符。方法也可以没有返回值，这时返回类型使用 `void`。

```csharp
public class Calculator
{
    // 定义一个加法方法
    public int Add(int a, int b)
    {
        return a + b;
    }

    // 定义一个无返回值的方法
    public void PrintSum(int a, int b)
    {
        Console.WriteLine($"Sum is: {a + b}");
    }
}
```

### 方法重载 (Method Overloading)

C# 支持方法重载，允许同名方法根据参数类型或数量不同进行重载。

```csharp
public class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }

    public double Add(double a, double b)
    {
        return a + b;
    }

    public string Add(string a, string b)
    {
        return a + b;
    }
}
```

### 静态方法 (Static Methods)

静态方法属于类而不是类的实例。你可以直接通过类名调用静态方法。

```csharp
public class MathUtils
{
    public static int Multiply(int a, int b)
    {
        return a * b;
    }
}
```

---

## 类的其他特性

### 垃圾回收 (Garbage Collection)

C# 具有自动垃圾回收机制，系统会自动管理内存和资源的释放。开发者无需手动管理内存释放，但可以使用 `Dispose()` 方法和 `using` 语句来手动释放一些非托管资源。

```csharp
public class FileManager : IDisposable
{
    private bool disposed = false;

    public void Dispose()
    {
        if (!disposed)
        {
            // 释放非托管资源
            disposed = true;
        }
    }
}
```

### 接口 (Interfaces)

接口在 C# 中是一种特殊的类型，它定义了类必须实现的成员。接口不包含字段或实现，只能包含方法、属性、事件或索引器的签名。

```csharp
public interface IDriveable
{
    void Drive();
}

public class Car : IDriveable
{
    public void Drive()
    {
        Console.WriteLine("Car is driving");
    }
}
```

---