---
title: 字符串内插 - C# 教程
description: 本教程介绍了如何使用 C# 字符串内插功能将格式化表达式结果添加到较大的字符串中。
author: rpetrusha
ms.author: ronpet
ms.date: 10/23/2018
ms.openlocfilehash: 97773659ea7dd00c291aa6a96401cac531adfdc8
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2019
ms.locfileid: "58921360"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a><span data-ttu-id="6977d-103">使用字符串内插构造格式化字符串</span><span class="sxs-lookup"><span data-stu-id="6977d-103">Use string interpolation to construct formatted strings</span></span>

<span data-ttu-id="6977d-104">本教程介绍了如何使用 C# [字符串内插](../../language-reference/tokens/interpolated.md)将值插入单个结果字符串中。</span><span class="sxs-lookup"><span data-stu-id="6977d-104">This tutorial teaches you how to use C# [string interpolation](../../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="6977d-105">读者可以编写 C# 代码并查看代码编译和运行结果。</span><span class="sxs-lookup"><span data-stu-id="6977d-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="6977d-106">本教程包含一系列课程，介绍了如何将值插入字符串，以及用不同方式设置这些值的格式。</span><span class="sxs-lookup"><span data-stu-id="6977d-106">The tutorial contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="6977d-107">本教程要求你有一台可用于开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="6977d-107">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="6977d-108">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="6977d-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="6977d-109">另外，还可在浏览器中完成本教程的[交互式版本](interpolated-strings.yml)。</span><span class="sxs-lookup"><span data-stu-id="6977d-109">You also can complete the [interactive version](interpolated-strings.yml) of this tutorial in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="6977d-110">创建内插字符串</span><span class="sxs-lookup"><span data-stu-id="6977d-110">Create an interpolated string</span></span>

<span data-ttu-id="6977d-111">创建名为 interpolated 的目录。</span><span class="sxs-lookup"><span data-stu-id="6977d-111">Create a directory named **interpolated**.</span></span> <span data-ttu-id="6977d-112">将其设置为当前目录并从控制台窗口运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6977d-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="6977d-113">此命令会在当前目录中创建一个新的 .NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6977d-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="6977d-114">在常用编辑器中，打开 Program.cs，将行 `Console.WriteLine("Hello World!");` 替换为以下代码，并将 `<name>` 替换为你的姓名 ：</span><span class="sxs-lookup"><span data-stu-id="6977d-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="6977d-115">通过在控制台窗口键入 `dotnet run` 试运行此代码。</span><span class="sxs-lookup"><span data-stu-id="6977d-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="6977d-116">当运行该程序时，它会在问候语中显示一个包含你的姓名的字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="6977d-117"><xref:System.Console.WriteLine%2A> 方法调用中包含的字符串是一个内插字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="6977d-118">这是一种模板，可让你用包含嵌入代码的字符串构造单个字符串（称为结果字符串）。</span><span class="sxs-lookup"><span data-stu-id="6977d-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="6977d-119">内插字符串特别适用于将值插入字符串或连接字符串（将字符串联在一起）。</span><span class="sxs-lookup"><span data-stu-id="6977d-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="6977d-120">该简单示例包含了每个内插字符串必须具有的两个元素：</span><span class="sxs-lookup"><span data-stu-id="6977d-120">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="6977d-121">字符串文本以 `$` 字符开头，后接左双引号字符。</span><span class="sxs-lookup"><span data-stu-id="6977d-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="6977d-122">`$` 符号和引号字符之间不能有空格。</span><span class="sxs-lookup"><span data-stu-id="6977d-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="6977d-123">（如果希望看到包含空格会发生什么情况，请在 `$` 字符后面插入一个空格并保存该文件，然后在控制台窗口中键入 `dotnet run` 再次运行该程序。</span><span class="sxs-lookup"><span data-stu-id="6977d-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="6977d-124">C# 编译器显示错误消息“错误 CS1056:意外的字符 '$'”。）</span><span class="sxs-lookup"><span data-stu-id="6977d-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="6977d-125">一个或多个内插表达式。</span><span class="sxs-lookup"><span data-stu-id="6977d-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="6977d-126">左大括号和右大括号（`{` 和 `}`）指示内插表达式。</span><span class="sxs-lookup"><span data-stu-id="6977d-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="6977d-127">可将任何返回值的 C# 表达式置于大括号内（包括 `null`）。</span><span class="sxs-lookup"><span data-stu-id="6977d-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="6977d-128">下面再尝试一些其他数据类型的字符串内插示例。</span><span class="sxs-lookup"><span data-stu-id="6977d-128">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="6977d-129">包含不同的数据类型</span><span class="sxs-lookup"><span data-stu-id="6977d-129">Include different data types</span></span>

<span data-ttu-id="6977d-130">上一节使用了字符串内插将一个字符串插入到了另一字符串中。</span><span class="sxs-lookup"><span data-stu-id="6977d-130">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="6977d-131">不过，内插字符串表达式的结果可以是任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="6977d-131">The result of an interpolated expression can be of any data type, though.</span></span> <span data-ttu-id="6977d-132">下面让我们在内插字符串中添加多种数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="6977d-132">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="6977d-133">在以下示例中，首先定义一个具有 `Name` [属性](../../properties.md)和 `ToString` [方法](../../methods.md)的[类](../../programming-guide/classes-and-structs/classes.md)数据类型 `Vegetable`，它可以[替代](../../language-reference/keywords/override.md) <xref:System.Object.ToString?displayProperty=nameWithType> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="6977d-133">In the following example, we first define a [class](../../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has a `Name` [property](../../properties.md) and a `ToString` [method](../../methods.md), which [overrides](../../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6977d-134">[`public` 访问修饰符](../../language-reference/keywords/public.md)使该方法可用于任何客户端代码以获取 `Vegetable` 实例的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="6977d-134">The [`public` access modifier](../../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="6977d-135">在本示例中，`Vegetable.ToString` 方法返回在 `Vegetable` [构造函数](../../programming-guide/classes-and-structs/constructors.md)处初始化的 `Name` 属性的值：</span><span class="sxs-lookup"><span data-stu-id="6977d-135">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="6977d-136">然后，通过使用 [`new` 关键字](../../language-reference/keywords/new-operator.md)并为构造函数 `Vegetable` 提供一个名称来创建名为 `item` 的 `Vegetable` 类的实例：</span><span class="sxs-lookup"><span data-stu-id="6977d-136">Then we create an instance of the `Vegetable` class named `item` by using the [`new` keyword](../../language-reference/keywords/new-operator.md) and providing a name for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="6977d-137">最后，将 `item` 变量添加到同样包含 <xref:System.DateTime> 值、<xref:System.Decimal> 值和 `Unit` [枚举](../../programming-guide/enumeration-types.md)值的内插字符串中。</span><span class="sxs-lookup"><span data-stu-id="6977d-137">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="6977d-138">将编辑器中的所有 C# 代码替换为以下代码，然后使用 `dotnet run` 命令运行：</span><span class="sxs-lookup"><span data-stu-id="6977d-138">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

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

<span data-ttu-id="6977d-139">注意，内插字符串中的内插表达式 `item` 会解析为结果字符串中的“eggplant”文本。</span><span class="sxs-lookup"><span data-stu-id="6977d-139">Note that the interpolated expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="6977d-140">这是因为，当表达式结果的类型不是字符串时，会按照以下方式将其解析为字符串：</span><span class="sxs-lookup"><span data-stu-id="6977d-140">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="6977d-141">如果内插表达式的计算结果为 `null`，则会使用一个空字符串（"" 或 <xref:System.String.Empty?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="6977d-141">If the interpolated expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="6977d-142">如果内插表达式的计算结果不是 `null`，通常会调用结果类型的 `ToString` 方法。</span><span class="sxs-lookup"><span data-stu-id="6977d-142">If the interpolated expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="6977d-143">可以通过更新 `Vegetable.ToString` 方法的实现来进行测试。</span><span class="sxs-lookup"><span data-stu-id="6977d-143">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="6977d-144">你甚至不用实现 `ToString` 方法，因为每个类型都有一些此方法的实现。</span><span class="sxs-lookup"><span data-stu-id="6977d-144">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="6977d-145">可通过注释掉示例中 `Vegetable.ToString` 方法的定义（在它前面添加注释符号 `//` 即可）来进行测试。</span><span class="sxs-lookup"><span data-stu-id="6977d-145">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="6977d-146">在输出中，字符串“eggplant”被替换为完全限定的类型名称（本示例中为“Vegetable”），这是 <xref:System.Object.ToString?displayProperty=nameWithType> 方法的默认行为。</span><span class="sxs-lookup"><span data-stu-id="6977d-146">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6977d-147">对于枚举值的 `ToString` 方法，其默认行为是返回该值的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="6977d-147">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="6977d-148">在此示例的输出中，日期过于精确（eggplant 的价格不会以秒为单位变化），且价格值没有标明货币单位。</span><span class="sxs-lookup"><span data-stu-id="6977d-148">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="6977d-149">下一节将介绍如何通过控制表达式结果的字符串表示形式来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="6977d-149">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="6977d-150">控制内插表达式的格式</span><span class="sxs-lookup"><span data-stu-id="6977d-150">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="6977d-151">上一节将两个格式不正确的字符串插入到了结果字符串中。</span><span class="sxs-lookup"><span data-stu-id="6977d-151">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="6977d-152">一个是日期和时间值，只有日期是合适的。</span><span class="sxs-lookup"><span data-stu-id="6977d-152">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="6977d-153">第二个是没有标明货币单位的价格。</span><span class="sxs-lookup"><span data-stu-id="6977d-153">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="6977d-154">这两个问题都很容易解决。</span><span class="sxs-lookup"><span data-stu-id="6977d-154">Both issues are easy to address.</span></span> <span data-ttu-id="6977d-155">通过字符串内插，可以指定用于控制特定类型格式的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-155">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="6977d-156">将前面示例中的调用修改为 `Console.WriteLine`，从而包含日期和价格表达式的格式字符串，如以下行所示：</span><span class="sxs-lookup"><span data-stu-id="6977d-156">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="6977d-157">可通过在内插表达式后接冒号（“:”）和格式字符串来指定格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-157">You specify a format string by following the interpolated expression with a colon (":") and the format string.</span></span> <span data-ttu-id="6977d-158">“d”是[标准日期和时间格式字符串](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier)，表示短日期格式。</span><span class="sxs-lookup"><span data-stu-id="6977d-158">"d" is a [standard date and time format string](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="6977d-159">“C2”是[标准数值格式字符串](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier)，用数字表示货币值（精确到小数点后两位）。</span><span class="sxs-lookup"><span data-stu-id="6977d-159">"C2" is a  [standard numeric format string](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="6977d-160">.NET 库中的许多类型支持一组预定义的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-160">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="6977d-161">这些格式字符串包括所有数值类型以及日期和时间类型。</span><span class="sxs-lookup"><span data-stu-id="6977d-161">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="6977d-162">有关支持格式字符串的完整类型列表，请参阅 [.NET 中的格式化类型](../../../standard/base-types/formatting-types.md)文章中的[格式字符串和. NET 类库类型](../../../standard/base-types/formatting-types.md#stringRef)。</span><span class="sxs-lookup"><span data-stu-id="6977d-162">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="6977d-163">尝试在文本编辑器中修改格式字符串，并在每次更改时重新运行该程序，查看更改如何影响日期和时间以及数值的格式。</span><span class="sxs-lookup"><span data-stu-id="6977d-163">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="6977d-164">将 `{date:d}` 中的“d”更改为“t”（显示短时间格式）、“y”（显示年份和月份）和“yyyy”（显示四位数年份）。</span><span class="sxs-lookup"><span data-stu-id="6977d-164">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="6977d-165">将 `{price:C2}` 中的“C2”更改为“e”（用于指数计数法）和“F3”（使数值在小数点后保持三位数字）。</span><span class="sxs-lookup"><span data-stu-id="6977d-165">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="6977d-166">除了控制格式之外，还可以控制结果字符串中包含的格式字符串的字段宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="6977d-166">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="6977d-167">下一节会介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6977d-167">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="6977d-168">控制内插表达式的字段宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="6977d-168">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="6977d-169">通常，当内插表达式的结果格式化为字符串时，结果字符串中会包含该字符串，但没有前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="6977d-169">Ordinarily, when the result of an interpolated expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="6977d-170">特别是对于使用一组数据的情况，控制字段宽度和对齐方式有助于增强输出的可读性。</span><span class="sxs-lookup"><span data-stu-id="6977d-170">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="6977d-171">为此，用下方代码替换文本编辑器中的所有代码，然后键入 `dotnet run` 来执行程序：</span><span class="sxs-lookup"><span data-stu-id="6977d-171">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

<span data-ttu-id="6977d-172">创建者姓名采用左对齐方式，其所写标题采用右对齐方式。</span><span class="sxs-lookup"><span data-stu-id="6977d-172">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="6977d-173">通过在内插表达式后面添加一个逗号（“,”）并指定“最小”字段宽度来指定对齐方式。</span><span class="sxs-lookup"><span data-stu-id="6977d-173">You specify the alignment by adding a comma (",") after an interpolated expression and designating the *minimum* field width.</span></span> <span data-ttu-id="6977d-174">如果指定的值是正数，则该字段为右对齐。</span><span class="sxs-lookup"><span data-stu-id="6977d-174">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="6977d-175">如果它为负数，则该字段为左对齐。</span><span class="sxs-lookup"><span data-stu-id="6977d-175">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="6977d-176">尝试删除 `{"Author",-25}` 和 `{title.Key,-25}` 代码中的负号，然后再次运行该示例，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="6977d-176">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="6977d-177">此时，创建者信息为右对齐。</span><span class="sxs-lookup"><span data-stu-id="6977d-177">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="6977d-178">可合并单个内插表达式中的对齐说明符和格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-178">You can combine an alignment specifier and a format string for a single interpolated expression.</span></span> <span data-ttu-id="6977d-179">为此，请先指定对齐方式，然后是冒号和格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-179">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="6977d-180">将 `Main` 方法中的所有代码替换为以下代码，该代码用定义的字段宽度显示格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="6977d-180">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="6977d-181">然后输入 `dotnet run` 命令来运行程序。</span><span class="sxs-lookup"><span data-stu-id="6977d-181">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="6977d-182">输出类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="6977d-182">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="6977d-183">你已完成“字符串内插”教程。</span><span class="sxs-lookup"><span data-stu-id="6977d-183">You've completed the string interpolation tutorial.</span></span>

<span data-ttu-id="6977d-184">有关详细信息，请参阅[字符串内插](../../language-reference/tokens/interpolated.md)主题和 [C# 中的字符串内插](../../tutorials/string-interpolation.md)教程。</span><span class="sxs-lookup"><span data-stu-id="6977d-184">For more information, see the [String interpolation](../../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial.</span></span>
