
# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 声明对象

在 C# 中，声明对象通常是通过类来创建实例。你可以通过使用 `new` 关键字来声明和实例化对象。声明对象的方式可以根据需求有所不同。

### 1. 使用 `new` 关键字声明对象

最常见的对象声明方式是通过 `new` 关键字，结合构造函数来实例化一个类的对象。

```csharp
// 声明并实例化一个 Person 类的对象
Person person1 = new Person("John", 30);
```

在这个例子中，`Person` 是一个类，`person1` 是一个该类的实例对象，`new Person("John", 30)` 会调用 `Person` 类的构造函数，并将 `"John"` 和 `30` 作为参数传递给构造函数。

### 2. 声明对象但不立即实例化

你也可以声明一个对象但不立即实例化，之后再通过 `new` 关键字来实例化它。

```csharp
Person person2;  // 声明对象，但没有实例化
person2 = new Person("Alice", 25);  // 后续实例化
```

### 3. 声明数组并实例化

如果需要创建对象的数组，可以使用以下语法：

```csharp
Person[] people = new Person[3];  // 声明一个 Person 类型的数组，长度为 3
people[0] = new Person("John", 30);  // 初始化数组中的元素
people[1] = new Person("Alice", 25);
people[2] = new Person("Bob", 40);
```

### 4. 使用对象初始化器

C# 还提供了对象初始化器语法，可以在声明对象的同时对对象的属性进行初始化，而不需要调用构造函数。

```csharp
Person person3 = new Person
{
    Name = "Charlie",
    Age = 35
};
```

这种方式不需要显式调用构造函数，而是直接为对象的属性赋值。对象初始化器为类的公共属性和字段提供了一个简便的初始化方式。

### 5. 匿名对象

C# 允许你创建匿名对象，尤其适用于仅需要存储一些临时数据的场景。匿名对象不需要显式声明类型，编译器会根据属性自动推断类型。

```csharp
var anonymousPerson = new { Name = "David", Age = 28 };
Console.WriteLine($"Name: {anonymousPerson.Name}, Age: {anonymousPerson.Age}");
```

在这个例子中，`anonymousPerson` 是一个匿名类型的对象，它有 `Name` 和 `Age` 两个属性。

### 6. 使用构造函数初始化对象

当你声明对象时，可以传递参数给构造函数，以初始化对象的成员。构造函数允许你在创建对象时指定一些初始值。

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // 带参构造函数
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

// 创建对象时传递参数
Person person4 = new Person("Eve", 22);
```

### 7. 默认构造函数

如果没有定义任何构造函数，C# 会为你提供一个默认的无参数构造函数，这样你可以创建对象而不需要传递任何参数。

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

// 使用默认构造函数
Person person5 = new Person();
person5.Name = "Frank";
person5.Age = 33;
```

### 8. 构造函数重载

你还可以定义多个构造函数，根据不同的参数来初始化对象的不同状态。

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
    
    // 默认构造函数
    public Person() { }
    
    // 带参数的构造函数
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

// 使用不同的构造函数来初始化对象
Person person6 = new Person("Grace", 29);  // 调用带参构造函数
Person person7 = new Person();             // 调用默认构造函数
```

---

