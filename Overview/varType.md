以下是整理后的 C# 文档：

---

# C# 基础教程

## 版权信息
© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

## 1. C# 基本语法

- **基本语法**：C# 的基本语法和 C/C++ 类似。
- **转义字符**：C# 的转义字符规则与 C/C++ 一致，如 `\n` 表示换行。
- **预处理指令**：C# 中的预处理指令用法与 C/C++ 类似。

### 示例：折叠代码块
```c#
#region 
// your code 
#endregion // 表示折叠代码块
```

---

## 2. 变量类型

| 变量类型  | 后缀  | 描述                                      |
|-----------|-------|-------------------------------------------|
| `sbyte`   | --    | 字节类型，取值 -128 ~ +127，相当于 C/C++ 中的 `int8_t` |
| `byte`    | --    | 相当于 C/C++ 中的 `uint8_t`              |
| `short`   | --    | 相当于 C/C++ 中的 `int16_t` / `short`    |
| `ushort`  | --    | 相当于 C/C++ 中的 `uint16_t`             |
| `long`    | L     | 长整型，64 位整数，表示范围大于 `int`   |
| `ulong`   | UL    | 无符号长整型，64 位无符号整数            |
| `int`     | --    | 32 位整数，常用的整型类型                |
| `uint`    | U     | 无符号 32 位整数，相当于 C/C++ 中的 `uint32_t` |
| `float`   | F     | 单精度浮点数，32 位                      |
| `double`  | D     | 双精度浮点数，64 位                      |
| `decimal` | M     | 十进制数类型，通常用于财务计算，高精度浮点数 |
| `char`    | --    | 字符类型，表示单个 Unicode 字符          |
| `bool`    | --    | 布尔值类型，表示 `true` 或 `false`       |
| `string`  | --    | 字符串类型，表示字符序列                |

---

## 3. 字符串操作

### 3.1 字符串转义规则
C# 使用与 C/C++ 相同的转义规则。例如，`\n` 表示换行。

### 3.2 字符串插值
字符串插值允许直接在字符串中插入变量值，格式为：`$"字符串{变量}"`。

#### 示例：
```c#
string username = "pxf";
Console.WriteLine($"Welcome {username}!");
```

### 3.3 逐字字符串
通过在字符串前加 `@` 符号，可以处理多行字符串，并保留换行符和空格。

#### 示例：
```c#
string multilineString = @"This is 
a multi-line string 
with special characters \n and spaces.";
```

### 3.4 字符串拼接
C# 支持用 `+` 符号进行字符串拼接，但建议使用字符串插值进行更清晰和简洁的代码。

#### 示例：
```c#
string firstName = "John";
string lastName = "Doe";
Console.WriteLine($"Hello, {firstName} {lastName}!");
```

### 3.5 字符串转换为数字
可以使用 `Convert.ToInt32()` 和 `Convert.ToDouble()` 将字符串转换为数字。

#### 示例：
```c#
string intString = "123";
string floatString = "45.67";
int intNum = Convert.ToInt32(intString);
double floatNum = Convert.ToDouble(floatString);
```

---
