
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

### 结构

1. **定义一个结构体类型**：
   结构体用于封装不同数据类型的成员。它类似于类，但结构体是值类型。你可以像下面这样定义一个结构体：

   ```c#
   struct MyStruct
   {
       int number1;
       float number2;
   }
   ```

2. **结构体访问权限**：
   - 默认情况下，结构体的成员是`private`，这意味着外部无法直接访问它们。如果你希望成员能够被外部访问，需要使用`public`访问修饰符。

   - **示例**：
     ```c#
     struct Point
     {
         public int x;
         public int y;
     }

     Point myPoint;
     myPoint.x = 10;  // 通过 public 访问修饰符可以访问成员
     myPoint.y = 20;
     ```

   在这个例子中，结构体 `Point` 有两个成员 `x` 和 `y`，都被声明为 `public`，所以它们可以在结构体外部直接访问。

### 3. **为结构体类型创建别名**

在 C# 中，可以使用 `using` 关键字为结构体类型创建别名，这类似于 C/C++ 中的 `typedef`。

#### 示例：为结构体类型创建别名

```c#
using PointAlias = Point;

PointAlias p1 = new PointAlias();  // 使用别名创建结构体变量
p1.x = 10;
p1.y = 20;
```

在此示例中，我们使用 `using` 关键字将 `Point` 类型创建了一个别名 `PointAlias`。这样我们就可以使用 `PointAlias` 来引用 `Point` 类型。

- 可以使用 `using` 为结构体类型创建别名。
- `using` 关键字能够为结构体类型提供类似于 C/C++ 中 `typedef` 的功能。
- `using`这种方法不仅能为结构体创建别名，还能为类、枚举等创建别名
---
