
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 接口 (Interfaces)

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