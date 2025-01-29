
---

# C# 编程指南

## 版权信息

© 2024. 未经许可不得复制、修改或分发。此文献为 [小風的藏書閣](https://t.me/xfp2333) 所有。

---

```xml
<Window x:Class="RemindAPP.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:RemindAPP"
        mc:Ignorable="d"
        Title="小風的日记" Height="500" Width="600"
        Icon="D:\C#\project\RemindAPP\favicon.ico">
    <!-- 设置窗口的背景图像 -->
    <Window.Background>
        <ImageBrush x:Name="background" ImageSource="D:\C#\project\RemindAPP\background4.jpg"/>
    </Window.Background>

    <!-- 窗口的主布局，使用 Grid 布局 -->
    <Grid>
        <!-- 设置 Grid 的列定义，第一列宽度固定为 200px，第二列自适应剩余空间 -->
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="200"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>

        <!-- 左侧导航栏 -->
        <StackPanel Grid.Column="0" Background="#80000000" VerticalAlignment="Stretch">
            <!-- 显示标题，便签 -->
            <TextBlock Text="📌 便签" FontSize="18" Foreground="White" Margin="10"/>
            
            <!-- 新建按钮，点击时触发 NEWText_button 方法 -->
            <Button x:Name="New_text" Content="✏️ 新建" Height="40" Margin="5" Background="#FFAA66" Foreground="White" Click="NEWText_button"/>
            
            <!-- 日程按钮，点击时触发 Schedule_button 方法 -->
            <Button Name="checkText" Content="📅 日程" Height="40" Margin="5" Background="#FFAA66" Foreground="White" Click="Schedule_button"/>
            
            <!-- 备忘录按钮，点击时触发 checkText_button 方法 -->
            <Button Content="📝 备忘录" Height="40" Margin="5" Background="#FFAA66" Foreground="White" Click="checkText_button"/>
            
            <!-- 任务清单按钮 -->
            <Button Content="✅ 任务清单" Height="40" Margin="5" Background="#FFAA66" Foreground="White"/>
            
            <!-- 设置按钮 -->
            <Button Content="⚙ 设置" Height="40" Margin="5" Background="#FFAA66" Foreground="White"/>
        </StackPanel>

        <!-- 右侧内容区 -->
        <Grid Grid.Column="1">
            <!-- 日记区域，初始时设置为不可见 -->
            <StackPanel x:Name="DiaryContent" Visibility="Collapsed">
                <!-- 显示日记标题 -->
                <TextBlock Text="📖 我的日记" FontSize="20" FontWeight="Bold" Foreground="Black"/>
                
                <!-- 输入框，支持换行和自动换行 -->
                <TextBox TextWrapping="Wrap" AcceptsReturn="True" VerticalScrollBarVisibility="Auto" Height="400" Background="#FFFFE0" BorderBrush="Transparent"/>
                
                <!-- 保存按钮，点击时保存日记 -->
                <Button Content="💾 保存" HorizontalAlignment="Right" Padding="10,5" Background="#66CC99" Foreground="White"/>
            </StackPanel>

            <!-- 日历区域 -->
            <StackPanel>
                <!-- 自定义日历控件 -->
                <Calendar x:Name="CalendarContent" Visibility="Visible" HorizontalAlignment="Center" Width="305">
                    <!-- 设置日历的样式 -->
                    <Calendar.Style>
                        <Style TargetType="Calendar">
                            <!-- 设置日历的背景颜色 -->
                            <Setter Property="Background" Value="#FFEB3B" />
                            
                            <!-- 设置日历的字体 -->
                            <Setter Property="FontFamily" Value="Segoe UI" />
                            <Setter Property="FontSize" Value="14" />
                            <Setter Property="Foreground" Value="Black" />
                            
                            <!-- 设置选中日期按钮的样式 -->
                            <Setter Property="CalendarDayButtonStyle">
                                <Setter.Value>
                                    <Style TargetType="Button">
                                        <!-- 设置选中日期按钮的背景色为浅蓝 -->
                                        <Setter Property="Background" Value="LightBlue" />
                                        <Setter Property="Foreground" Value="Black" />
                                        <!-- 设置按钮字体大小为16 -->
                                        <Setter Property="FontSize" Value="16" />
                                    </Style>
                                </Setter.Value>
                            </Setter>
                        </Style>
                    </Calendar.Style>
                </Calendar>
            </StackPanel>
        </Grid>
    </Grid>
</Window>
```

### 属性功能说明：

1. **Window：**
   - `x:Class`：指定该窗口类的名称。
   - `xmlns`：用于引入 XAML 命名空间。
   - `Title`：设置窗口的标题栏文本。
   - `Height`、`Width`：设置窗口的初始高度和宽度。
   - `Icon`：指定窗口的图标。

2. **Background：**
   - `ImageBrush`：设置窗口背景为图片，`ImageSource` 指定图片路径。

3. **Grid：**
   - `ColumnDefinitions`：定义 Grid 的列宽，其中第一列固定为 200px，第二列自适应宽度。

4. **StackPanel：**
   - `Grid.Column="0"`：将该 `StackPanel` 放置在 Grid 的第一列。
   - `Background`：设置背景颜色（半透明黑色 `#80000000`）。
   - `VerticalAlignment="Stretch"`：使 `StackPanel` 在垂直方向上填满父容器。

5. **Button：**
   - `x:Name`：给按钮一个名称，以便在代码中引用。
   - `Content`：设置按钮的显示文本或图标。
   - `Height`、`Margin`：设置按钮的高度和外边距。
   - `Background`、`Foreground`：设置按钮的背景和前景（文字）颜色。
   - `Click`：定义按钮点击时执行的方法。

6. **TextBlock：**
   - `Text`：设置显示的文本。
   - `FontSize`、`FontWeight`、`Foreground`：设置字体大小、加粗样式和字体颜色。
   - `Margin`：设置文本的外边距。

7. **TextBox：**
   - `TextWrapping="Wrap"`：启用文本换行。
   - `AcceptsReturn="True"`：允许用户按回车键输入多行文本。
   - `VerticalScrollBarVisibility="Auto"`：自动显示垂直滚动条。
   - `Height`、`Background`、`BorderBrush`：设置文本框的高度、背景色和边框样式。

8. **Calendar：**
   - `Visibility`：设置控件的可见性，初始为可见。
   - `HorizontalAlignment="Center"`：使日历居中对齐。
   - `Width`：设置日历的宽度。
   - `Style`：为日历定义样式，包括背景颜色、字体、选中日期按钮的样式等。

9. **Setter：**
   - `Property`：指定需要设置的属性（如背景色、字体、按钮样式等）。
   - `Value`：为属性赋值。

10. **CalendarDayButtonStyle：**
    - 通过 `Setter` 为日历日期按钮设置样式，控制选中日期按钮的背景色、字体颜色和大小。
