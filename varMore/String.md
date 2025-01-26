
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

# 处理字符串的更多方法

- `string`类型变量可以看作是`char`类型的数组

```c#
string myString = "A string";
char myChar = myString[0];  // 访问字符串中的第一个字符

// 将字符串转换为字符数组
char[] charArray = myString.ToCharArray();

char deleteChar = 'A';
// 获取字符串的长度
int length = myString.Length;

// 将字符串转为大写
string upperString = myString.ToUpper();

// 将字符串转为小写
string lowerString = myString.ToLower();

// 删除字符串前后的空格
string trimmedString = myString.Trim();

// 删除指定的字符
string trimmedCharString = myString.Trim(deleteChar);

// 使用 foreach 遍历字符串中的字符
foreach (char c in myString)
{
    // 你的代码
}

// 从字符串的左侧添加空格，使总长度为 10
string paddedLeft = myString.PadLeft(10); 

// 从字符串的左侧添加 '-'，使总长度为 10
string paddedLeftWithDash = myString.PadLeft(10, '-'); 

// 从字符串的右侧添加 '-'，使总长度为 10
string paddedRightWithDash = myString.PadRight(10, '-');
```

### 说明：
- `Length`：获取字符串的字符数。
- `ToUpper()`：将字符串转换为大写。
- `ToLower()`：将字符串转换为小写。
- `Trim()`：去除字符串前后空格。
- `Trim(char)`：去除字符串前后指定的字符。
- `PadLeft(int)`：在字符串的左侧填充空格，直到字符串长度为指定的值。
- `PadLeft(int, char)`：在字符串的左侧填充指定字符，直到字符串长度为指定的值。
- `PadRight(int, char)`：在字符串的右侧填充指定字符，直到字符串长度为指定的值。

---