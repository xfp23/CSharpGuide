# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 属性

属性（Property）是 C# 中的一种特殊方法，它使得对字段的访问能够像访问字段一样简洁，并且能够包含一些额外的逻辑。属性是通过 `get` 和 `set` 访问器来实现的。

在 C# 中，结构体（struct）和类（class）的属性有相似之处，但也有一些不同之处。下面分别介绍它们的属性。

## 1. 类属性

类属性与字段类似，但它们通常具有逻辑来控制访问。类中的属性可以有 **getter** 和 **setter**，允许对字段进行更细粒度的控制。类属性可以是自动属性，支持定义只读或只写属性。

### 1.1 基本语法

类中的属性通常使用 `get` 和 `set` 访问器来进行定义：

#### 语法：
```c#
public type PropertyName
{
    get { return field; }
    set { field = value; }
}
```

#### 示例：
```c#
public class Person
{
    private string name;

    public string Name
    {
        get { return name; }
        set { name = value; }
    }
}
```

在上面的示例中，`Name` 是一个普通的类属性，`get` 访问器返回 `name` 字段的值，`set` 访问器将新值赋给 `name` 字段。

### 1.2 自动属性

自动属性是类属性的一种简化形式，编译器会自动创建一个隐式的私有字段来存储属性的值。

#### 示例：
```c#
public class Person
{
    public string Name { get; set; }
}
```

在这个例子中，`Name` 是一个自动实现的属性，编译器为其创建了一个隐式字段来存储属性值。

### 1.3 只读和只写属性

类属性可以有只读或只写的访问器，控制外部对属性的修改权限。

#### 只读属性（只包含 `get`）：
```c#
public class Person
{
    private string name;

    public string Name
    {
        get { return name; }
    }

    public Person(string name)
    {
        this.name = name;
    }
}
```

在这个例子中，`Name` 属性只能通过构造函数赋值，外部无法修改。

#### 只写属性（只包含 `set`）：
```c#
public class Person
{
    private string name;

    public string Name
    {
        set { name = value; }
    }
}
```

在这个例子中，`Name` 只能通过 `set` 设置值，无法获取其值。

## 2. 结构体属性

结构体的属性与类属性的基本语法类似，但结构体的行为有一些特殊之处，尤其是在性能和内存分配方面。

### 2.1 基本语法

结构体中的属性也由 `get` 和 `set` 访问器构成，但结构体具有值类型特性，这意味着结构体在赋值时会进行值复制，而类则是引用类型。

#### 示例：
```c#
public struct Point
{
    private int x;
    private int y;

    public int X
    {
        get { return x; }
        set { x = value; }
    }

    public int Y
    {
        get { return y; }
        set { y = value; }
    }
}
```

在这个示例中，`Point` 结构体有两个属性 `X` 和 `Y`，通过 `get` 和 `set` 方法来访问其值。

### 2.2 自动属性

结构体也支持自动属性，但使用自动属性时，结构体会在内部创建一个隐藏字段来存储属性的值。

#### 示例：
```c#
public struct Point
{
    public int X { get; set; }
    public int Y { get; set; }
}
```

### 2.3 只读属性

结构体可以定义只读属性，它们的值只能在结构体构造时设置，之后无法修改。

#### 示例：
```c#
public struct Point
{
    private int x;
    private int y;

    public int X
    {
        get { return x; }
    }

    public int Y
    {
        get { return y; }
    }

    public Point(int x, int y)
    {
        this.x = x;
        this.y = y;
    }
}
```

在这个例子中，`X` 和 `Y` 是只读属性，它们的值只能在结构体的构造函数中进行初始化，之后无法修改。

### 2.4 性能考虑

由于结构体是值类型，它的实例在赋值时会被复制，因此结构体的属性访问通常比类的属性要高效。特别是在涉及大量数据时，结构体的属性更加节省内存。另一方面，类的属性在内存中是通过引用来存取的，因此类实例化的对象在性能上通常优于结构体（特别是在对象较大时）。

## 3. 总结

- **类属性**：类的属性通常具有 `get` 和 `set` 访问器，支持自动属性、只读属性、只写属性等灵活配置。类是引用类型，具有更多的功能。
- **结构体属性**：结构体的属性与类类似，但它是值类型，赋值时会进行值复制。结构体的属性通常用于性能优化，特别是在需要大量实例时。

无论是结构体还是类的属性，它们都使得数据的访问更加灵活，并能包含额外的逻辑。根据不同的需求，选择使用结构体或类的属性可以帮助你编写高效且易于维护的代码。