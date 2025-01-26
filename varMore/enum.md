### C# 编程指南

#### 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

### 枚举

C# 中的枚举（`enum`）沿用了 C 语言的设计，并做了一些扩展。

1. **枚举值本质上是整数类型**
   - C# 中，枚举的值本质上是整数类型，与 C 语言的规则相同。但是，C# 允许指定枚举的整数类型。默认情况下，C# 的枚举类型为 `int`，但是可以显式指定其他整数类型，包括：`byte`、`sbyte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`。

   - **语法**：
   ```c#
   enum <枚举类型名称> : <指定整数类型名称>
   {
       枚举值1,
       枚举值2,
       ...
   }
   ```
   
   - **示例**：
   ```c#
   enum Week : byte
   {
       Monday = 1,
       Tuesday = 2,
       Wednesday = 3,
       Thursday = 4,
       Friday = 5,
       Saturday = 6,
       Sunday = 7
   };

   Week myWeek = Week.Monday;  // 引用赋值
   Console.WriteLine(myWeek);   // 输出：Monday
   ```

2. **获取枚举的字符串表示**
   
   获取枚举的字符串表示可以通过以下方法：

   - **使用 `Convert` 类进行强类型转换**：
     ```c#
     enum Week : byte
     {
         Monday = 1,
         Tuesday = 2,
         Wednesday = 3,
         Thursday = 4,
         Friday = 5,
         Saturday = 6,
         Sunday = 7
     };

     Week myWeek = Week.Monday;
     string enumString = Convert.ToString(myWeek);
     Console.WriteLine(enumString);  // 输出：Monday
     ```

   - **使用 `ToString()` 方法**：
     ```c#
     enum Week : byte
     {
         Monday = 1,
         Tuesday = 2,
         Wednesday = 3,
         Thursday = 4,
         Friday = 5,
         Saturday = 6,
         Sunday = 7
     };

     Week myWeek = Week.Monday;
     string enumString = myWeek.ToString();
     Console.WriteLine(enumString);  // 输出：Monday
     ```

3. **枚举与整数的转换**
   
   枚举实际上是整数类型，可以进行转换：
   - **从枚举到整数**：
     ```c#
     int weekDay = (int)Week.Monday;
     Console.WriteLine(weekDay);  // 输出：1
     ```

   - **从整数到枚举**：
     ```c#
     Week myDay = (Week)1;  
     Console.WriteLine(myDay);  // 输出：Monday
     ```
