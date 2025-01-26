以下是整理后的 C# 编程指南，包含了流程控制部分：

---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

## 1. 流程控制

### 1.1 关系运算符
- 与 `C/C++` 中的关系运算符一致，用于比较两个值的大小、相等性等。

### 1.2 循环控制
- 循环控制结构（如 `for`、`while`、`do-while`）与 `C/C++` 中一致。

### 1.3 `if` 语句
- 在 `C#` 中，`if` 语句仅接受布尔类型 (`bool`) 的条件表达式，不能像 `C/C++` 中那样将非零值当作 `true` 来判断。

#### 示例：
```c#
bool condition = true;
if (condition)
{
    Console.WriteLine("Condition is true!");
}
else
{
    Console.WriteLine("Condition is false!");
}
```

### 1.4 `switch` 语句
- `switch` 语句在 `C#` 中与 `C/C++` 类似，但有一些差异：
  - 支持字符串（`string`）类型的分支。
  - 如果没有 `break`，需要显式地使用 `goto` 语句来跳转到下一个 `case`。
  - `default` 语句可以放在 `switch` 的任何位置，虽然推荐放在末尾。

#### 示例：
```c#
string name = "pxf";
switch(name)
{
    case "pxf":
        // your code
        // break; // 可选的 break
        goto case "xfp";  // 没有 break，则使用 goto 跳转到下一个 case
    case "xfp":
        break;
    default:
        break;
}
```

---

## 2. 总结
- **关系运算符**：与 `C/C++` 一致，简单易懂。
- **`if` 语句**：必须使用布尔值判断，避免将其他值当作真值。
- **`switch` 语句**：除了常规的整型和枚举类型支持外，`C#` 还支持字符串类型的分支，并且需要注意 `goto` 用法。

---

如果有任何问题，或需要进一步的示例，欢迎随时联系我！