
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 继承 (Inheritance)

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