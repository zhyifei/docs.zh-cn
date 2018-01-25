---
title: "快速入门 - 内插字符串 - C# 指南"
description: "在此内插字符串快速入门中，你需要编写 C# 代码以将表达式结果包含在较大字符串中。"
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 14185dd4e364f12756541ac6401d1c6ff3206fe9
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2018
---
# <a name="interpolated-strings"></a><span data-ttu-id="bd1a2-103">内插字符串</span><span class="sxs-lookup"><span data-stu-id="bd1a2-103">Interpolated strings</span></span>

<span data-ttu-id="bd1a2-104">本快速入门介绍如何在 C# 中使用内插字符串将值插入到单个输出字符串中。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-104">This quick start teaches you how to use interpolated strings in C# to insert values into a single ouput string.</span></span> <span data-ttu-id="bd1a2-105">读者可以编写 C# 代码并查看代码编译和运行结果。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="bd1a2-106">快速入门包含一系列课程，包括向字符串中插入值，以及用不同方式对这些值进行格式化。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-106">The quick start contains a series of lessons that insert values into strings, and format those values in different ways.</span></span>

<span data-ttu-id="bd1a2-107">本快速入门教程要求你有一台可用于开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-107">This quick start expects that you have a machine you can use for development.</span></span> <span data-ttu-id="bd1a2-108">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="bd1a2-109">[本地快速入门简介](local-environment.md)简要概述了你将用到的命令，还提供了详细信息链接。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-109">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span> 

## <a name="create-an-interpolated-string"></a><span data-ttu-id="bd1a2-110">创建内插字符串</span><span class="sxs-lookup"><span data-stu-id="bd1a2-110">Create an interpolated string</span></span>

<span data-ttu-id="bd1a2-111">创建名为 interpolated-quickstart 的目录。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-111">Create a directory named **interpolated-quickstart**.</span></span> <span data-ttu-id="bd1a2-112">将其设置为当前目录并从控制台窗口运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console -n interpolated -o .
```

<span data-ttu-id="bd1a2-113">此命令会在当前目录中创建一个新的 .NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="bd1a2-114">在常用编辑器中，打开 Program.cs，将行 `Console.WriteLine("Hello World!");` 替换为以下代码，并将 `<name>` 替换为你的姓名 ：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
<span data-ttu-id="bd1a2-115">通过在控制台窗口键入 `dotnet run` 试运行此代码。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="bd1a2-116">当运行该程序时，它会在问候语中显示一个包含你的姓名的字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="bd1a2-117"><xref:System.Console.WriteLine%2A> 方法调用中包含的字符串是一个内插字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="bd1a2-118">这是一种模板，可让你用包含嵌入代码的字符串构造单个字符串（称为结果字符串）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="bd1a2-119">内插字符串特别适用于将值插入字符串或连接字符串（将字符串联在一起）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span> 
    
<span data-ttu-id="bd1a2-120">该简单示例包含了每个内插字符串必须具有的两个元素：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-120">This simple example contains the two elements that every interpolated string must have:</span></span> 

- <span data-ttu-id="bd1a2-121">字符串文本以 `$` 字符开头，后接左双引号字符。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="bd1a2-122">`$` 符号和引号字符之间不能有空格。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="bd1a2-123">（如果希望看到包含空格会发生什么情况，请在 `$` 字符后面插入一个空格并保存该文件，然后在控制台窗口中键入 `dotnet run` 再次运行该程序。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="bd1a2-124">C# 编译器显示错误消息“错误 CS1056: 意外的字符 '$'”。）</span><span class="sxs-lookup"><span data-stu-id="bd1a2-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span> 

- <span data-ttu-id="bd1a2-125">一个或多个内插表达式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="bd1a2-126">左大括号和右大括号（`{` 和 `}`）指示内插表达式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="bd1a2-127">可将任何返回值的 C# 表达式置于大括号内（包括 `null`）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span> 

<span data-ttu-id="bd1a2-128">下面再尝试一些其他数据类型的内插字符串示例。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-128">Let's try a few more interpolated string examples with some other data types.</span></span>
    
## <a name="include-different-data-types"></a><span data-ttu-id="bd1a2-129">包含不同的数据类型</span><span class="sxs-lookup"><span data-stu-id="bd1a2-129">Include different data types</span></span>

<span data-ttu-id="bd1a2-130">上一节使用了内插字符串将一个字符串插入到了另一字符串中。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-130">In the previous section, you used an interpolated string to insert one string inside of another.</span></span> <span data-ttu-id="bd1a2-131">不过，内插字符串表达式可以是任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-131">An interpolated string expression can be any data type, though.</span></span> <span data-ttu-id="bd1a2-132">下面尝试一个具有多种数据类型值的内插字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-132">Let's try an interpolated string that has values of multiple data types.</span></span> 
    
<span data-ttu-id="bd1a2-133">以下示例包含带有 `Vegetable` 对象、`Unit` 枚举成员、<xref:System.DateTime> 值和 <xref:System.Decimal> 值的内插表达式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-133">The following example includes interpolated expressions with a `Vegetable` object, a member of the `Unit` enumeration, a <xref:System.DateTime> value, and a <xref:System.Decimal> value.</span></span> <span data-ttu-id="bd1a2-134">将编辑器中的所有 C# 代码替换为以下代码，然后使用 `console run` 命令运行：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-134">Replace all of the C# code in your editor with the following code, and then use the `console run` command to run it:</span></span>

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
    
<span data-ttu-id="bd1a2-135">请注意，第二个内插表达式包含控制台上显示的结果字符串中的 `item` 对象，在这种情况下，字符串“eggplant”将插入到结果字符串中。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-135">Note that the second interpolated expression includes the `item` object in the result string that's displayed to the console, and in this case the string "eggplant" is inserted into the result string.</span></span> <span data-ttu-id="bd1a2-136">这是因为，当内插表达式的类型不是字符串时，C# 编译器会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-136">That's because, when the type of an interpolated expression is not a string, the C# compiler does the following:</span></span>

- <span data-ttu-id="bd1a2-137">如果内插表达式为 `null`，内插表达式将返回一个空字符串（"" 或 <xref:System.String.Empty?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-137">If the interpolated expression is `null`, the interpolated expression returns an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>).</span></span>

- <span data-ttu-id="bd1a2-138">如果内插表达式不是 `null`，则调用内插表达式类型的 `ToString` 方法。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-138">If the interpolated expression is not `null`, the `ToString` method of the type of the interpolated expression is called.</span></span> <span data-ttu-id="bd1a2-139">你可以在内插表达式前面添加注释符号（`//`注释掉示例中的 `Vegetable.ToString` 方法的定义，以此方式来进行测试。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-139">You can test this by commenting out the definition of the `Vegetable.ToString` method in the example by putting a comment symbol (`//`) in front of it.</span></span> <span data-ttu-id="bd1a2-140">在输出中，字符串“eggplant”被替换为类型名称“Vegetable”，这是 <xref:System.Object.ToString?displayProperty=nameWithType> 方法的默认行为。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-140">In the output, the string "eggplant" is replaced by the type name, "Vegetable", which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span>   

<span data-ttu-id="bd1a2-141">在此示例的输出中，日期过于精确（eggplant 的价格不会以秒为单位变化），且价格值没有标明货币单位。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-141">In the output from this example, the date is too precise (the price of eggplant does not vary by the second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="bd1a2-142">下一节将介绍如何通过控制内插表达式返回的字符串格式来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-142">In the next section, you'll learn how to fix those issues by controlling the format of strings returned by interpolated expressions.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="bd1a2-143">控制内插表达式的格式</span><span class="sxs-lookup"><span data-stu-id="bd1a2-143">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="bd1a2-144">上一节将两个格式不正确的字符串插入到了结果字符串中。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-144">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="bd1a2-145">一个是日期和时间值，只有日期是合适的。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-145">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="bd1a2-146">另一个是价格没有标明货币单位。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-146">The second was a price that did not indicate its unit of currency.</span></span> <span data-ttu-id="bd1a2-147">这两个问题都很容易解决。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-147">Both issues are easy to address.</span></span> <span data-ttu-id="bd1a2-148">内插表达式可以包含控制特定类型格式的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-148">Interpolated expressions can include *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="bd1a2-149">将前面示例中的调用修改为 `Console.WriteLine`，以包含日期和价格字段的格式说明符，如以下行所示：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-149">Modify the call to `Console.WriteLine` from the previous example to include the format specifier for the date and price fields as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
<span data-ttu-id="bd1a2-150">可通过在内插表达式后接冒号和格式字符串来指定格式字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-150">You specify a format string by following the interpolated expression with a colon and the format string.</span></span> <span data-ttu-id="bd1a2-151">“d”是[标准日期和时间格式字符串](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier)，表示短日期格式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-151">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="bd1a2-152">“C2”是[标准数值格式字符串](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier)，用数字表示货币值（精确到小数点后两位）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-152">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="bd1a2-153">.NET Standard 库中的许多类型支持一组预定义的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-153">A number of types in the .NET Standard libraries support a predefined set of format strings.</span></span> <span data-ttu-id="bd1a2-154">这些格式字符串包括所有数值类型以及日期和时间类型。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-154">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="bd1a2-155">有关支持格式字符串的完整类型列表，请参阅 [.NET 中的格式化类型](../../standard/base-types/formatting-types.md)文章中的[格式字符串和. NET 类库类型](../../standard/base-types/formatting-types.md#stringRef)。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-155">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span> <span data-ttu-id="bd1a2-156">任何类型都可以支持一组格式字符串，你也可以开发自定义格式设置扩展，为现有类型提供自定义格式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-156">Any type can support a set of format strings, and you can also develop custom formatting extensions that provide custom formatting for existing types.</span></span> <span data-ttu-id="bd1a2-157">有关通过提供 <xref:System.ICustomFormatter> 实现进行自定义格式设置的信息，请参阅 [.NET 中的格式化类型](../../standard/base-types/formatting-types.md)文章中的[使用 ICustomFormatter 进行自定义格式设置](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-157">For information on custom formatting by providing an <xref:System.ICustomFormatter> implementation, see [Custom Formatting with ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="bd1a2-158">尝试在文本编辑器中修改格式字符串，并在每次更改时重新运行该程序，查看更改如何影响日期和时间以及数值的格式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-158">Try modifying the the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="bd1a2-159">将 `{date:d}` 中的“d”更改为“t”（显示短时间格式）、“y”（显示年份和月份）和“yyyy”（显示四位数年份）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-159">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="bd1a2-160">将 `{price:C2}` 中的“C2”更改为“e”（用于指数计数法）和“F3”（使数值在小数点后保持三位数字）。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-160">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="bd1a2-161">除了控制格式之外，还可以控制内插表达式返回字符串的字段宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-161">In addition to controlling formatting, you can also control the field width and alignment of the strings returned by an interpolated expression.</span></span> <span data-ttu-id="bd1a2-162">下一节会介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-162">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="bd1a2-163">控制内插表达式的字段宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="bd1a2-163">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="bd1a2-164">通常，当结果字符串中包含内插表达式返回的字符串时，该字符串没有前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-164">Ordinarily, when the string returned by an interpolated expression is included in a result string, it has no leading or trailing spaces.</span></span> <span data-ttu-id="bd1a2-165">特别是对于使用一组数据的情况，使用内插表达式可以指定字段宽度及其对齐方式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-165">Particularly for instances in which you are working with a set of data, interpolated expressions let you specify a field width and its alignment.</span></span> <span data-ttu-id="bd1a2-166">为此，用下方代码替换文本编辑器中的所有代码，然后键入 `console run` 来执行程序：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-166">To see this, replace all the code in your text editor with the following code, then type `console run` to execute the program:</span></span>
    
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
    
<span data-ttu-id="bd1a2-167">创建者姓名采用左对齐方式，其所写标题采用右对齐方式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-167">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="bd1a2-168">通过在表达式后面添加一个逗号 (",") 并指定字段宽度来指定对齐方式。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-168">You specify the alignment by adding a comma (",") after the expression and designating the field width.</span></span> <span data-ttu-id="bd1a2-169">如果字段宽度是正数，则该字段为右对齐：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-169">If the field width is a positive number, the field is right-aligned:</span></span>

```text
{expression, width}
```

<span data-ttu-id="bd1a2-170">如果字段宽度是负数，则该字段为左对齐：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-170">If the field width is a negative number, the field is left-aligned:</span></span>

```text
{expression, -width}
```

<span data-ttu-id="bd1a2-171">尝试删除 `{"Author",-25}` 和 `{title.Key,-25}` 内插表达式中的负号，然后再次运行该示例，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-171">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` interpolated expressions and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
```

<span data-ttu-id="bd1a2-172">此时，创建者信息为右对齐。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-172">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="bd1a2-173">可在单个内插表达式中合并字段宽度和格式字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-173">You can combine a field width and a format string in a single interpolated expression.</span></span> <span data-ttu-id="bd1a2-174">字段宽度在前，后接冒号和格式字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-174">The field width comes first, followed by a colon and the format string.</span></span> <span data-ttu-id="bd1a2-175">将 `Main` 方法中的所有代码替换为以下代码，该代码用定义的字段宽度显示格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-175">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="bd1a2-176">然后输入 `dotnet run` 命令来运行程序。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-176">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
<span data-ttu-id="bd1a2-177">输出类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="bd1a2-177">The output looks something like the following:</span></span>

```console
1/11/2018            Hour 09                1,063.34 feet
```

<span data-ttu-id="bd1a2-178">你已完成内插字符串快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-178">You've completed the interpolated strings quick start.</span></span> 
    
<span data-ttu-id="bd1a2-179">可以继续在你自己的开发环境中学习[数组和集合](arrays-and-collections.md)快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-179">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="bd1a2-180">可在 C# 参考的[内插字符串](../language-reference/keywords/interpolated-strings.md)主题中了解有关使用内插字符串的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bd1a2-180">You can learn more about working with interpolated strings in the [Interpolated Strings](../language-reference/keywords/interpolated-strings.md) topic in the C# Reference.</span></span>

