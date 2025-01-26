
---

# 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 一个简单的`c#`程序

```c#
using system; // 告诉编译器使用system中的类

namespace simple // 创建一个命名空间
{
    class  program // 声明一个类
    {
        static void Main() // main方法
        {
            Console.writeLine("hello world !");
        }
    }
}
```

2. 介绍:

1. 没有第一行的`using`,编译器就不知道该区哪里找Console控件，相当于`C/C++`的`#include`预处理指令

2. C#程序由一个或多个类组成，比如上述程序，由`program`类组成。

3. 名称空间是与每个名称相关联的一组类的声明

4. 标识符命名规则与`c/c++`相同

# C# 中的关键字

| 关键字       | 描述                                      |
|--------------|-------------------------------------------|
| `abstract`   | 声明抽象类或方法                            |
| `as`         | 用于类型转换                               |
| `base`       | 访问基类成员                               |
| `bool`       | 布尔类型                                   |
| `break`      | 退出循环或switch语句                      |
| `byte`       | 字节类型                                   |
| `case`       | 定义switch语句中的条件                     |
| `catch`      | 捕获异常                                   |
| `char`       | 字符类型                                   |
| `checked`    | 强制执行溢出检查                           |
| `class`      | 声明一个类                                 |
| `const`      | 声明常量                                   |
| `continue`   | 结束当前循环并进入下一次循环               |
| `decimal`    | 十进制数类型（高精度浮点数）               |
| `default`    | 指定switch语句中的默认值                  |
| `delegate`   | 声明委托                                   |
| `do`         | 循环语句，先执行一次再检查条件             |
| `double`     | 双精度浮点数类型                           |
| `else`       | if语句的备用条件                          |
| `enum`       | 枚举类型                                   |
| `event`      | 声明事件                                   |
| `explicit`   | 强制类型转换方法的声明                    |
| `extern`     | 声明外部方法                               |
| `false`      | 布尔值假                                   |
| `finally`    | 定义在异常处理中的清理代码                 |
| `fixed`      | 用于固定内存地址的指针                     |
| `for`        | 循环语句                                   |
| `foreach`    | 遍历集合的元素                             |
| `goto`       | 跳转到代码中的某个标签位置                |
| `if`         | 条件语句                                   |
| `implicit`   | 隐式类型转换                               |
| `in`         | 用于遍历集合或作为输入参数传递给方法      |
| `int`        | 整数类型                                   |
| `interface`  | 声明接口                                   |
| `internal`   | 指定类、方法等的访问范围为程序集内        |
| `is`         | 检查对象是否为某个类型                     |
| `long`       | 长整型数据类型                             |
| `namespace`  | 声明命名空间                               |
| `new`        | 创建对象实例                               |
| `null`       | 空值                                       |
| `object`     | 所有类型的基类                             |
| `operator`   | 定义操作符的方法                           |
| `out`        | 方法参数，表示输出参数                    |
| `override`   | 重写基类的方法                             |
| `params`     | 允许传递可变数量的参数                     |
| `private`    | 限制成员的访问权限                         |
| `protected`  | 限制成员的访问权限，允许子类访问           |
| `public`     | 公共访问权限                               |
| `readonly`   | 声明只读字段                               |
| `ref`        | 引用参数                                   |
| `return`     | 返回方法的值                               |
| `sbyte`      | 有符号字节类型                             |
| `sealed`     | 防止类被继承                               |
| `short`      | 短整型数据类型                             |
| `sizeof`     | 获取数据类型的大小                         |
| `stackalloc` | 在栈上分配内存                            |
| `static`     | 声明静态成员                               |
| `string`     | 字符串类型                                 |
| `struct`     | 声明结构体                                 |
| `switch`     | 条件语句                                   |
| `this`       | 引用当前对象                               |
| `throw`      | 抛出异常                                   |
| `try`        | 尝试执行代码并捕获异常                     |
| `typeof`     | 获取类型的Type对象                         |
| `uint`       | 无符号整型数据类型                         |
| `ulong`      | 无符号长整型数据类型                       |
| `unsafe`     | 启用不安全代码                             |
| `using`      | 引用命名空间、定义资源管理器               |
| `void`       | 无返回值类型                               |
| `volatile`   | 表示字段值可能会被外部因素改变             |
| `while`      | 循环语句，先检查条件后执行循环             |

---
