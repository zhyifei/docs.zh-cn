---
title: "“内插的字符串”教程 - C# 本地快速入门"
description: "在“内插的字符串”本快速入门教程中，编写 C# 代码，将表达式结果添加到更大的字符串中。"
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: b6089b69eb350fce29f86f19f5abeb44acb4b6b4
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="interpolated-strings"></a>内插字符串

本快速入门教程介绍了如何在 C# 中使用内插的字符串，将值插入单个输出字符串中。 读者可以编写 C# 代码并查看代码编译和运行结果。 本快速入门教程包含一系列课程，包括将值插入字符串，以及用不同方式设置这些值的格式。

若要学习本快速入门教程，必须有开发计算机。 .NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。 [本地快速入门教程简介](local-environment.md)不仅简要概述了将用到的命令，还收录了详细信息链接。 

## <a name="create-an-interpolated-string"></a>创建内插字符串

创建名为 interpolated-quickstart 的目录。 将其设置为当前目录并从控制台窗口运行以下命令：

```console
dotnet new console -n interpolated -o .
```

此命令会在当前目录中创建一个新的 .NET Core 控制台应用程序。

在常用编辑器中，打开 Program.cs，将行 `Console.WriteLine("Hello World!");` 替换为以下代码，并将 `<name>` 替换为你的姓名 ：

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
通过在控制台窗口键入 `dotnet run` 试运行此代码。 当运行该程序时，它会在问候语中显示一个包含你的姓名的字符串。 <xref:System.Console.WriteLine%2A> 方法调用中包含的字符串是一个内插字符串。 这是一种模板，可让你用包含嵌入代码的字符串构造单个字符串（称为结果字符串）。 内插字符串特别适用于将值插入字符串或连接字符串（将字符串联在一起）。 
    
该简单示例包含了每个内插字符串必须具有的两个元素： 

- 字符串文本以 `$` 字符开头，后接左双引号字符。 `$` 符号和引号字符之间不能有空格。 （如果希望看到包含空格会发生什么情况，请在 `$` 字符后面插入一个空格并保存该文件，然后在控制台窗口中键入 `dotnet run` 再次运行该程序。 C# 编译器显示错误消息“错误 CS1056: 意外的字符 '$'”。） 

- 一个或多个内插表达式。 左大括号和右大括号（`{` 和 `}`）指示内插表达式。 可将任何返回值的 C# 表达式置于大括号内（包括 `null`）。 

下面再尝试一些其他数据类型的内插字符串示例。
    
## <a name="include-different-data-types"></a>包含不同的数据类型

上一节使用了内插字符串将一个字符串插入到了另一字符串中。 不过，内插字符串表达式可以是任何数据类型。 下面尝试一个具有多种数据类型值的内插字符串。 
    
以下示例包含带有 `Vegetable` 对象、`Unit` 枚举成员、<xref:System.DateTime> 值和 <xref:System.Decimal> 值的内插表达式。 将编辑器中的所有 C# 代码替换为以下代码，然后使用 `console run` 命令运行：

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```
    
请注意，第二个内插表达式包含控制台上显示的结果字符串中的 `item` 对象，在这种情况下，字符串“eggplant”将插入到结果字符串中。 这是因为，当内插表达式的类型不是字符串时，C# 编译器会执行以下操作：

- 如果内插表达式为 `null`，内插表达式将返回一个空字符串（"" 或 <xref:System.String.Empty?displayProperty=nameWithType>）。

- 如果内插表达式不是 `null`，则调用内插表达式类型的 `ToString` 方法。 你可以在内插表达式前面添加注释符号（`//`注释掉示例中的 `Vegetable.ToString` 方法的定义，以此方式来进行测试。 在输出中，字符串“eggplant”被替换为类型名称“Vegetable”，这是 <xref:System.Object.ToString?displayProperty=nameWithType> 方法的默认行为。   

在此示例的输出中，日期过于精确（eggplant 的价格不会以秒为单位变化），且价格值没有标明货币单位。 下一节将介绍如何通过控制内插表达式返回的字符串格式来解决这些问题。

## <a name="control-the-formatting-of-interpolated-expressions"></a>控制内插表达式的格式

上一节将两个格式不正确的字符串插入到了结果字符串中。 一个是日期和时间值，只有日期是合适的。 另一个是价格没有标明货币单位。 这两个问题都很容易解决。 内插表达式可以包含控制特定类型格式的格式字符串。 将前面示例中的调用修改为 `Console.WriteLine`，以包含日期和价格字段的格式说明符，如以下行所示：

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
可通过在内插表达式后接冒号和格式字符串来指定格式字符串。 “d”是[标准日期和时间格式字符串](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier)，表示短日期格式。 “C2”是[标准数值格式字符串](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier)，用数字表示货币值（精确到小数点后两位）。

.NET Standard 库中的许多类型支持一组预定义的格式字符串。 这些格式字符串包括所有数值类型以及日期和时间类型。 有关支持格式字符串的完整类型列表，请参阅 [.NET 中的格式化类型](../../standard/base-types/formatting-types.md)文章中的[格式字符串和. NET 类库类型](../../standard/base-types/formatting-types.md#stringRef)。 任何类型都可以支持一组格式字符串，你也可以开发自定义格式设置扩展，为现有类型提供自定义格式。 有关通过提供 <xref:System.ICustomFormatter> 实现进行自定义格式设置的信息，请参阅 [.NET 中的格式化类型](../../standard/base-types/formatting-types.md)文章中的[使用 ICustomFormatter 进行自定义格式设置](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)。

尝试在文本编辑器中修改格式字符串，并在每次更改时重新运行该程序，查看更改如何影响日期和时间以及数值的格式。 将 `{date:d}` 中的“d”更改为“t”（显示短时间格式）、“y”（显示年份和月份）和“yyyy”（显示四位数年份）。 将 `{price:C2}` 中的“C2”更改为“e”（用于指数计数法）和“F3”（使数值在小数点后保持三位数字）。

除了控制格式之外，还可以控制内插表达式返回字符串的字段宽度和对齐方式。 下一节会介绍如何执行此操作。

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a>控制内插表达式的字段宽度和对齐方式

通常，当结果字符串中包含内插表达式返回的字符串时，该字符串没有前导或尾随空格。 特别是对于使用一组数据的情况，使用内插表达式可以指定字段宽度及其对齐方式。 为此，用下方代码替换文本编辑器中的所有代码，然后键入 `console run` 来执行程序：
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
创建者姓名采用左对齐方式，其所写标题采用右对齐方式。 通过在表达式后面添加一个逗号 (",") 并指定字段宽度来指定对齐方式。 如果字段宽度是正数，则该字段为右对齐：

```text
{expression, width}
```

如果字段宽度是负数，则该字段为左对齐：

```text
{expression, -width}
```

尝试删除 `{"Author",-25}` 和 `{title.Key,-25}` 内插表达式中的负号，然后再次运行该示例，如以下代码所示：

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

此时，创建者信息为右对齐。

可在单个内插表达式中合并字段宽度和格式字符串。 字段宽度在前，后接冒号和格式字符串。 将 `Main` 方法中的所有代码替换为以下代码，该代码用定义的字段宽度显示格式化字符串。 然后输入 `dotnet run` 命令来运行程序。

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
输出类似于以下内容：

```console
1/11/2018            Hour 09                1,063.34 feet
```

已完成“内插的字符串”快速入门教程。 
    
可以在自己的开发环境中继续学习[数组和集合](arrays-and-collections.md)快速入门教程。

可在 C# 参考的[内插字符串](../language-reference/keywords/interpolated-strings.md)主题中了解有关使用内插字符串的详细信息。

