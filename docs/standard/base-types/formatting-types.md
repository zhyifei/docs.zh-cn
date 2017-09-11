---
title: "格式设置类型"
description: "格式设置类型"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
ms.translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: e9b8ad13a48dd43236769b130d6f8a75b7b023ca
ms.contentlocale: zh-cn
ms.lasthandoff: 03/10/2017

---

# <a name="formatting-types"></a><span data-ttu-id="82f2f-104">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="82f2f-104">Formatting types</span></span>

<span data-ttu-id="82f2f-105">格式设置是指将类、结构或枚举值的实例转换为其字符串表示形式的过程，通常使得最终的字符串可以显示给用户，或者进行反序列化以还原为原始数据类型。</span><span class="sxs-lookup"><span data-stu-id="82f2f-105">Formatting is the process of converting an instance of a class, structure, or enumeration value to its string representation, often so that the resulting string can be displayed to users or deserialized to restore the original data type.</span></span> <span data-ttu-id="82f2f-106">此转换可能面临一系列挑战：</span><span class="sxs-lookup"><span data-stu-id="82f2f-106">This conversion can pose a number of challenges:</span></span>

* <span data-ttu-id="82f2f-107">在内部存储值的方式不一定反映用户想要查看它们的方式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-107">The way that values are stored internally does not necessarily reflect the way that users want to view them.</span></span> <span data-ttu-id="82f2f-108">例如，电话号码可以存储为 **8009999999** 格式，但此格式并非是用户友好的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-108">For example, a telephone number might be stored in the form **8009999999**, which is not user-friendly.</span></span> <span data-ttu-id="82f2f-109">该电话号码应显示为 **800-999-9999**。</span><span class="sxs-lookup"><span data-stu-id="82f2f-109">It should instead be displayed as **800-999-9999**.</span></span> <span data-ttu-id="82f2f-110">有关以这种方式设置数字格式的示例，请参见[自定义格式字符串](#custom-format-strings)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-110">See the [Custom format strings](#custom-format-strings) section for an example that formats a number in this way.</span></span> 

* <span data-ttu-id="82f2f-111">有时对象到其字符串表示形式的转换不是直观的。</span><span class="sxs-lookup"><span data-stu-id="82f2f-111">Sometimes the conversion of an object to its string representation is not intuitive.</span></span> <span data-ttu-id="82f2f-112">例如，不清楚 **Temperature** 对象或 **Person** 对象的字符串表示形式应如何显示。</span><span class="sxs-lookup"><span data-stu-id="82f2f-112">For example, it is not clear how the string representation of a **Temperature** object or a **Person** object should appear.</span></span> <span data-ttu-id="82f2f-113">有关以各种方式设置 **Temperature** 对象格式的示例，请参见[标准格式字符串](#standard-format-strings)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-113">For an example that formats a **Temperature** object in a variety of ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

* <span data-ttu-id="82f2f-114">值通常需要区分区域性的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-114">Values often require culture-sensitive formatting.</span></span> <span data-ttu-id="82f2f-115">例如，在使用数字表示货币值的应用程序中，数字字符串应包括当前区域性的货币符号、组分隔符（在大多数区域性中，组分隔符为千位分隔符）和小数点符号。</span><span class="sxs-lookup"><span data-stu-id="82f2f-115">For example, in an application that uses numbers to reflect monetary values, numeric strings should include the current culture’s currency symbol, group separator (which, in most cultures, is the thousands separator), and decimal symbol.</span></span> <span data-ttu-id="82f2f-116">有关示例，请参见[使用格式提供程序和 IFormatProvider 接口进行区分区域性的格式设置](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-116">For an example, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span> 

* <span data-ttu-id="82f2f-117">应用程序可能需要以不同方式显示相同的值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-117">An application may have to display the same value in different ways.</span></span> <span data-ttu-id="82f2f-118">例如，应用程序可能通过显示名称的字符串表示形式来表示一个枚举成员，或通过显示基础值来表示该枚举成员。</span><span class="sxs-lookup"><span data-stu-id="82f2f-118">For example, an application may represent an enumeration member by displaying a string representation of its name or by displaying its underlying value.</span></span> <span data-ttu-id="82f2f-119">有关以不同方式设置 [DayOfWeek](xref:System.DayOfWeek) 枚举数量格式的示例，请参见[标准格式字符串](#standard-format-strings)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-119">For an example that formats a member of the [DayOfWeek](xref:System.DayOfWeek) enumeration in different ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

<span data-ttu-id="82f2f-120">.NET 提供了丰富的格式设置支持，使得开发人员可以满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="82f2f-120">.NET provides rich formatting support that enables developers to address these requirements.</span></span> 

> [!NOTE]
> <span data-ttu-id="82f2f-121">格式设置将类型的值转换为字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-121">Formatting converts the value of a type into a string representation.</span></span> <span data-ttu-id="82f2f-122">分析是格式设置的反向操作。</span><span class="sxs-lookup"><span data-stu-id="82f2f-122">Parsing is the inverse of formatting.</span></span> <span data-ttu-id="82f2f-123">分析操作根据数据类型的字符串表示形式创建该数据类型的实例。</span><span class="sxs-lookup"><span data-stu-id="82f2f-123">A parsing operation creates an instance of a data type from its string representation.</span></span> <span data-ttu-id="82f2f-124">有关将字符串转换成其他数据类型的信息，请参见[分析字符串](parsing-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-124">For information about converting strings to other data types, see [Parsing strings](parsing-strings.md).</span></span>

<span data-ttu-id="82f2f-125">本概述包含以下几节：</span><span class="sxs-lookup"><span data-stu-id="82f2f-125">This overview contains the following sections:</span></span>

* [<span data-ttu-id="82f2f-126">.NET 中的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-126">Formatting in .NET</span></span>](#formatting-in-net)

* [<span data-ttu-id="82f2f-127">使用 ToString 方法的默认格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-127">Default formatting using the ToString method</span></span>](#default-formatting-using-the-tostring-method)

* [<span data-ttu-id="82f2f-128">重写 ToString 方法</span><span class="sxs-lookup"><span data-stu-id="82f2f-128">Overriding the ToString method</span></span>](#overriding-the-tostring-method)

* [<span data-ttu-id="82f2f-129">ToString 方法和格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-129">The ToString method and format strings</span></span>](#the-tostring-method-and-format-strings)

    * [<span data-ttu-id="82f2f-130">标准格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-130">Standard format strings</span></span>](#standard-format-strings)
    
    * [<span data-ttu-id="82f2f-131">自定义格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-131">Custom format strings</span></span>](#custom-format-strings)
    
    * [<span data-ttu-id="82f2f-132">格式字符串和 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="82f2f-132">Format strings and .NET types</span></span>](#format-strings-and-net-types)
    
* [<span data-ttu-id="82f2f-133">使用格式提供程序和 IFormatProvider 接口的区分区域性的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-133">Culture-sensitive formatting with format providers and the IFormatProvider interface</span></span>](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [<span data-ttu-id="82f2f-134">数值的区分区域性的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-134">Culture-sensitive formatting of numeric values</span></span>](#culture-sensitive-formatting-of-numeric-values)
    
    * [<span data-ttu-id="82f2f-135">日期和时间值的区分区域性的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-135">Culture-sensitive formatting of date and time values</span></span>](#culture-sensitive-formatting-of-date-and-time-values)
    
* [<span data-ttu-id="82f2f-136">IFormattable 接口</span><span class="sxs-lookup"><span data-stu-id="82f2f-136">The IFormattable interface</span></span>](#the-iformattable-interface)

* [<span data-ttu-id="82f2f-137">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-137">Composite formatting</span></span>](#composite-formatting)

* [<span data-ttu-id="82f2f-138">使用 ICustomFormatter 进行自定义格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-138">Custom formatting with ICustomFormatter</span></span>](#custom-formatting-with-icustomformatter)

* [<span data-ttu-id="82f2f-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="82f2f-139">Related topics</span></span>](#related-topics)

* [<span data-ttu-id="82f2f-140">参考</span><span class="sxs-lookup"><span data-stu-id="82f2f-140">Reference</span></span>](#reference)

## <a name="formatting-in-net"></a><span data-ttu-id="82f2f-141">.NET 中的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-141">Formatting in .NET</span></span>

<span data-ttu-id="82f2f-142">格式设置的基本机制是 [Object.ToString](xref:System.Object.ToString) 方法的默认实现，该方法在本主题后面的[使用 ToString 方法的默认格式设置](#default-formatting-using-the-tostring-method)部分中讨论。</span><span class="sxs-lookup"><span data-stu-id="82f2f-142">The basic mechanism for formatting is the default implementation of the [Object.ToString](xref:System.Object.ToString) method, which is discussed in the [Default formatting using the ToString method](#default-formatting-using-the-tostring-method) section later in this topic.</span></span> <span data-ttu-id="82f2f-143">不过，.NET 提供了几种方法来修改和扩展其默认格式设置支持。</span><span class="sxs-lookup"><span data-stu-id="82f2f-143">However, .NET provides several ways to modify and extend its default formatting support.</span></span> <span data-ttu-id="82f2f-144">这些要求包括：</span><span class="sxs-lookup"><span data-stu-id="82f2f-144">These include the following:</span></span>

* <span data-ttu-id="82f2f-145">重写 [Object.ToString](xref:System.Object.ToString) 方法以定义对象值的自定义字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-145">Overriding the [Object.ToString](xref:System.Object.ToString) method to define a custom string representation of an object’s value.</span></span> <span data-ttu-id="82f2f-146">有关更多信息，请参见本主题后面 [重写 ToString 方法](#overriding-the-tostring-method)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-146">For more information, see the [Overriding the ToString method](#overriding-the-tostring-method) section later in this topic.</span></span>

* <span data-ttu-id="82f2f-147">定义格式说明符，格式说明符允许对象值的字符串表示形式采用多种形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-147">Defining format specifiers that enable the string representation of an object’s value to take multiple forms.</span></span> <span data-ttu-id="82f2f-148">例如，以下语句中的“X”格式说明符将整数转换为十六进制值的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-148">For example, the "X" format specifier in the following statement converts an integer to the string representation of a hexadecimal value.</span></span>

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  <span data-ttu-id="82f2f-149">有关格式说明符的更多信息，请参见 [ToString 方法和格式字符串](#the-tostring-method-and-format-strings)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-149">For more information about format specifiers, see the [The ToString method and format strings](#the-tostring-method-and-format-strings) section.</span></span>
  
* <span data-ttu-id="82f2f-150">使用格式提供程序以利用特定区域性的格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-150">Using format providers to take advantage of the formatting conventions of a specific culture.</span></span> <span data-ttu-id="82f2f-151">例如，以下语句通过使用 en-US 区域性的格式设置约定来显示货币值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-151">For example, the following statement displays a currency value by using the formatting conventions of the en-US culture.</span></span> 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  <span data-ttu-id="82f2f-152">有关使用格式提供程序进行格式设置的更多信息，请参见[使用格式提供程序和 IFormatProvider 接口的区分区域性的格式设置](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-152">For more information about formatting with format providers, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span>  
  
* <span data-ttu-id="82f2f-153">实现 [IFormattable](xref:System.IFormattable) 接口可以支持使用 [Convert](xref:System.Convert) 类的字符串转换以及复合格式设置。</span><span class="sxs-lookup"><span data-stu-id="82f2f-153">Implementing the [IFormattable](xref:System.IFormattable) interface to support both string conversion with the [Convert](xref:System.Convert) class and composite formatting.</span></span> <span data-ttu-id="82f2f-154">有关更多信息，请参见 [IFormattable 接口](#the-iformattable-interface)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-154">For more information, see the [The IFormattable interface](#the-iformattable-interface) section.</span></span>

* <span data-ttu-id="82f2f-155">使用复合格式设置来嵌入较大字符串中值的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-155">Using composite formatting to embed the string representation of a value in a larger string.</span></span> <span data-ttu-id="82f2f-156">有关更多信息，请参见[复合格式设置](#composite-formatting)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-156">For more information, see the [Composite formatting](#composite-formatting) section.</span></span>

* <span data-ttu-id="82f2f-157">实现 [ICustomFormatter](xref:System.ICustomFormatter) 和 [IFormatProvider](xref:System.IFormatProvider) 可以提供完全自定义的格式设置解决方案。</span><span class="sxs-lookup"><span data-stu-id="82f2f-157">Implementing [ICustomFormatter](xref:System.ICustomFormatter) and [IFormatProvider](xref:System.IFormatProvider) to provide a complete custom formatting solution.</span></span> <span data-ttu-id="82f2f-158">有关更多信息，请参见[使用 ICustomFormatter 进行自定义格式设置](#custom-formatting-with-icustomformatter)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-158">For more information, see the [Custom formatting with ICustomFormatter](#custom-formatting-with-icustomformatter) section.</span></span>

<span data-ttu-id="82f2f-159">以下各部分分别使用这些方法来将对象转换为其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-159">The following sections examine these methods for converting an object to its string representation.</span></span>

## <a name="default-formatting-using-the-tostring-method"></a><span data-ttu-id="82f2f-160">使用 ToString 方法的默认格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-160">Default formatting using the ToString method</span></span>

<span data-ttu-id="82f2f-161">每个从 [System.Object](xref:System.Object) 派生的类型都自动继承无参数的 [ToString](xref:System.Object.ToString) 方法，该方法在默认情况下返回类型的名称。</span><span class="sxs-lookup"><span data-stu-id="82f2f-161">Every type that is derived from [System.Object](xref:System.Object) automatically inherits a parameterless [ToString](xref:System.Object.ToString) method, which returns the name of the type by default.</span></span> <span data-ttu-id="82f2f-162">下面的示例演示默认 [ToString](xref:System.Object.ToString) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-162">The following example illustrates the default [ToString](xref:System.Object.ToString) method.</span></span> <span data-ttu-id="82f2f-163">它定义一个名为 `Automobile`、不具有实现的类。</span><span class="sxs-lookup"><span data-stu-id="82f2f-163">It defines a class named `Automobile` that has no implementation.</span></span> <span data-ttu-id="82f2f-164">当对该类进行实例化并调用其 [ToString](xref:System.Object.ToString) 方法时，它显示其类型名称。</span><span class="sxs-lookup"><span data-stu-id="82f2f-164">When the class is instantiated and its [ToString](xref:System.Object.ToString) method is called, it displays its type name.</span></span> <span data-ttu-id="82f2f-165">请注意，此示例中未显式调用 [ToString](xref:System.Object.ToString) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-165">Note that the [ToString](xref:System.Object.ToString) method is not explicitly called in the example.</span></span> <span data-ttu-id="82f2f-166">[Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) 方法隐式调用作为参数传递给它的对象的 [ToString](xref:System.Object.ToString) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-166">The [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) method implicitly calls the [ToString](xref:System.Object.ToString) method of the object passed to it as an argument.</span></span> 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

<span data-ttu-id="82f2f-167">由于除接口以外的所有类型都派生自 [Object](xref:System.Object)，因此会向自定义类或结构自动提供此功能。</span><span class="sxs-lookup"><span data-stu-id="82f2f-167">Because all types other than interfaces are derived from [Object](xref:System.Object), this functionality is automatically provided to your custom classes or structures.</span></span> <span data-ttu-id="82f2f-168">但是，由默认 [ToString](xref:System.Object.ToString) 方法提供的功能具有以下限制：尽管它标识类型，但无法提供有关该类型的实例的任何信息。</span><span class="sxs-lookup"><span data-stu-id="82f2f-168">However, the functionality offered by the default [ToString](xref:System.Object.ToString) method, is limited: Although it identifies the type, it fails to provide any information about an instance of the type.</span></span> <span data-ttu-id="82f2f-169">若要提供可提供该对象相关信息的对象的字符串表示形式，必须重写 [ToString](xref:System.Object.ToString) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-169">To provide a string representation of an object that provides information about that object, you must override the [ToString](xref:System.Object.ToString) method.</span></span>

> [!NOTE]
> <span data-ttu-id="82f2f-170">结构继承自 [ValueType](xref:System.ValueType)，而后者又派生自 [Object](xref:System.Object)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-170">Structures inherit from [ValueType](xref:System.ValueType), which in turn is derived from [Object](xref:System.Object).</span></span> <span data-ttu-id="82f2f-171">虽然 [ValueType](xref:System.ValueType) 会重写 [Object.ToString](xref:System.Object.ToString)，但是其实现是相同。</span><span class="sxs-lookup"><span data-stu-id="82f2f-171">Although [ValueType](xref:System.ValueType) overrides [Object.ToString](xref:System.Object.ToString), its implementation is identical.</span></span>

## <a name="overriding-the-tostring-method"></a><span data-ttu-id="82f2f-172">重写 ToString 方法</span><span class="sxs-lookup"><span data-stu-id="82f2f-172">Overriding the ToString method</span></span>

<span data-ttu-id="82f2f-173">显示类型的名称这一用法往往有限，它不允许类型使用者区分实例。</span><span class="sxs-lookup"><span data-stu-id="82f2f-173">Displaying the name of a type is often of limited use and does not allow consumers of your types to differentiate one instance from another.</span></span> <span data-ttu-id="82f2f-174">但是，你可以重写 [ToString](xref:System.Object.ToString) 方法，以提供更有用的对象值表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-174">However, you can override the [ToString](xref:System.Object.ToString) method to provide a more useful representation of an object’s value.</span></span> <span data-ttu-id="82f2f-175">下面的示例定义 `Temperature` 对象并重写其 [ToString](xref:System.Object.ToString) 方法，以便以摄氏度显示温度。</span><span class="sxs-lookup"><span data-stu-id="82f2f-175">The following example defines a `Temperature` object and overrides its [ToString](xref:System.Object.ToString) method to display the temperature in degrees Celsius.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

<span data-ttu-id="82f2f-176">在 .NET 中，已重写每个基元值类型的 [ToString](xref:System.Object.ToString) 方法来显示对象的值而非其名称。</span><span class="sxs-lookup"><span data-stu-id="82f2f-176">In .NET, the [ToString](xref:System.Object.ToString) method of each primitive value type has been overridden to display the object’s value instead of its name.</span></span> <span data-ttu-id="82f2f-177">下表显示每种基元类型的重写。</span><span class="sxs-lookup"><span data-stu-id="82f2f-177">The following table shows the override for each primitive type.</span></span> <span data-ttu-id="82f2f-178">请注意，大多数重写方法调用 [ToString](xref:System.Object.ToString) 方法的另一个重载并向其传递用于定义其类型的一般格式的“G”格式说明符和表示当前区域性的 [IFormatProvider](xref:System.IFormatProvider) 对象。</span><span class="sxs-lookup"><span data-stu-id="82f2f-178">Note that most of the overridden methods call another overload of the [ToString](xref:System.Object.ToString) method and pass it the "G" format specifier, which defines the general format for its type, and an [IFormatProvider](xref:System.IFormatProvider) object that represents the current culture.</span></span>

<span data-ttu-id="82f2f-179">类型</span><span class="sxs-lookup"><span data-stu-id="82f2f-179">Type</span></span> | <span data-ttu-id="82f2f-180">ToString 重写</span><span class="sxs-lookup"><span data-stu-id="82f2f-180">ToString override</span></span>
---- | -----------------
[<span data-ttu-id="82f2f-181">布尔值</span><span class="sxs-lookup"><span data-stu-id="82f2f-181">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="82f2f-182">返回 [Boolean.TrueString](xref:System.Boolean.TrueString) 或 [Boolean.FalseString](xref:System.Boolean.FalseString)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-182">Returns either [Boolean.TrueString](xref:System.Boolean.TrueString) or [Boolean.FalseString](xref:System.Boolean.FalseString).</span></span>
[<span data-ttu-id="82f2f-183">Byte</span><span class="sxs-lookup"><span data-stu-id="82f2f-183">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="82f2f-184">调用 `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Byte](xref:System.Byte) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-184">Calls `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Byte](xref:System.Byte) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-185">Char</span><span class="sxs-lookup"><span data-stu-id="82f2f-185">Char</span></span>](xref:System.Char) | <span data-ttu-id="82f2f-186">以字符串形式返回字符。</span><span class="sxs-lookup"><span data-stu-id="82f2f-186">Returns the character as a string.</span></span>
[<span data-ttu-id="82f2f-187">DateTime</span><span class="sxs-lookup"><span data-stu-id="82f2f-187">DateTime</span></span>](xref:System.DateTime) | <span data-ttu-id="82f2f-188">调用 `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` 可以为当前区域性设置日期和时间值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-188">Calls `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` to format the date and time value for the current culture.</span></span> 
[<span data-ttu-id="82f2f-189">小数</span><span class="sxs-lookup"><span data-stu-id="82f2f-189">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="82f2f-190">调用 `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Decimal](xref:System.Decimal) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-190">Calls `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Decimal](xref:System.Decimal) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-191">双精度</span><span class="sxs-lookup"><span data-stu-id="82f2f-191">Double</span></span>](xref:System.Double) | <span data-ttu-id="82f2f-192">调用 `Double.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Double](xref:System.Double) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-192">Calls `Double.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Double](xref:System.Double) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-193">Int16</span><span class="sxs-lookup"><span data-stu-id="82f2f-193">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="82f2f-194">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Int16](xref:System.Int16) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-194">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int16](xref:System.Int16) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-195">Int32</span><span class="sxs-lookup"><span data-stu-id="82f2f-195">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="82f2f-196">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Int32](xref:System.Int32) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-196">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int32](xref:System.Int32) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-197">Int64</span><span class="sxs-lookup"><span data-stu-id="82f2f-197">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="82f2f-198">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Int64](xref:System.Int64) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-198">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int64](xref:System.Int64) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-199">SByte</span><span class="sxs-lookup"><span data-stu-id="82f2f-199">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="82f2f-200">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [SByte](xref:System.SByte)</span><span class="sxs-lookup"><span data-stu-id="82f2f-200">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [SByte](xref:System.SByte)</span></span> | <span data-ttu-id="82f2f-201">值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-201">value for the current culture.</span></span>
[<span data-ttu-id="82f2f-202">单精度</span><span class="sxs-lookup"><span data-stu-id="82f2f-202">Single</span></span>](xref:System.Single) | <span data-ttu-id="82f2f-203">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [Single](xref:System.Single) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-203">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Single](xref:System.Single) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-204">UInt32</span><span class="sxs-lookup"><span data-stu-id="82f2f-204">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="82f2f-205">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [UInt32](xref:System.UInt32) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-205">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32)value for the current culture.</span></span>
[<span data-ttu-id="82f2f-206">UInt32</span><span class="sxs-lookup"><span data-stu-id="82f2f-206">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="82f2f-207">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [UInt32](xref:System.UInt32) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-207">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32) value for the current culture.</span></span>
[<span data-ttu-id="82f2f-208">UInt64</span><span class="sxs-lookup"><span data-stu-id="82f2f-208">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="82f2f-209">调用 `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` 可以为当前区域性设置 [UInt64](xref:System.UInt64) 值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-209">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt64](xref:System.UInt64)  value for the current culture.</span></span>

## <a name="the-tostring-method-and-format-strings"></a><span data-ttu-id="82f2f-210">ToString 方法和格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-210">The ToString method and format strings</span></span>

<span data-ttu-id="82f2f-211">对象具有单一字符串表示形式时，可以依赖于默认 [ToString](xref:System.Object.ToString) 方法或重写 [ToString](xref:System.Object.ToString)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-211">Relying on the default [ToString](xref:System.Object.ToString) method or overriding [ToString](xref:System.Object.ToString) is appropriate when an object has a single string representation.</span></span> <span data-ttu-id="82f2f-212">但是，对象的值通常具有多种表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-212">However, the value of an object often has multiple representations.</span></span> <span data-ttu-id="82f2f-213">例如，温度可以用华氏度、摄氏度或开氏度来表示。</span><span class="sxs-lookup"><span data-stu-id="82f2f-213">For example, a temperature can be expressed in degrees Fahrenheit, degrees Celsius, or kelvins.</span></span> <span data-ttu-id="82f2f-214">同样，整数值 10 可以表示为多种形式，包括 10、10.0、1.0e01 或 $10.00。</span><span class="sxs-lookup"><span data-stu-id="82f2f-214">Similarly, the integer value 10 can be represented in numerous ways, including 10, 10.0, 1.0e01, or $10.00.</span></span>

<span data-ttu-id="82f2f-215">为了允许单个值具有多种字符串表示形式，.NET 使用格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-215">To enable a single value to have multiple string representations, .NET uses format strings.</span></span> <span data-ttu-id="82f2f-216">格式字符串是包含一个或多个预定义格式说明符的字符串，这些格式说明符是单一字符或字符组，用于定义 [ToString](xref:System.Object.ToString) 方法应如何设置其输出格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-216">A format string is a string that contains one or more predefined format specifiers, which are single characters or groups of characters that define how the [ToString](xref:System.Object.ToString) method should format its output.</span></span> <span data-ttu-id="82f2f-217">然后将格式字符串作为参数传递给对象的 [ToString](xref:System.Object.ToString) 方法，并确定应如何显示该对象值的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-217">The format string is then passed as a parameter to the object's [ToString](xref:System.Object.ToString) method and determines how the string representation of that object's value should appear.</span></span>

<span data-ttu-id="82f2f-218">.NET 中的所有数字类型、日期和时间类型以及枚举类型都支持一组预定义的格式说明符。</span><span class="sxs-lookup"><span data-stu-id="82f2f-218">All numeric types, date and time types, and enumeration types in .NET support a predefined set of format specifiers.</span></span> <span data-ttu-id="82f2f-219">还可以使用格式字符串定义你应用程序所定义的数据类型的多种字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-219">You can also use format strings to define multiple string representations of your application-defined data types.</span></span>

### <a name="standard-format-strings"></a><span data-ttu-id="82f2f-220">标准格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-220">Standard format strings</span></span>

<span data-ttu-id="82f2f-221">标准格式字符串包含单个格式说明符，该格式说明符是一个字母字符，用于定义应用该格式说明符的对象的字符串表示形式，此外，它还包含一个可选的精度说明符，该精度说明符影响在结果字符串中显示的位数。</span><span class="sxs-lookup"><span data-stu-id="82f2f-221">A standard format string contains a single format specifier, which is an alphabetic character that defines the string representation of the object to which it is applied, along with an optional precision specifier that affects how many digits are displayed in the result string.</span></span> <span data-ttu-id="82f2f-222">如果省略或不支持精度说明符，则标准格式说明符等效于标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-222">If the precision specifier is omitted or is not supported, a standard format specifier is equivalent to a standard format string.</span></span> 

<span data-ttu-id="82f2f-223">.NET 为所有数字类型、所有日期和时间类型以及所有枚举类型定义一组标准格式说明符。</span><span class="sxs-lookup"><span data-stu-id="82f2f-223">.NET defines a set of standard format specifiers for all numeric types, all date and time types, and all enumeration types.</span></span> <span data-ttu-id="82f2f-224">例如，这些类别中的每一类别都支持“G”标准格式说明符，该标准格式说明符定义该类型的值的一般字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-224">For example, each of these categories supports a "G" standard format specifier, which defines a general string representation of a value of that type.</span></span>

<span data-ttu-id="82f2f-225">枚举类型的标准格式字符串直接控制值的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-225">Standard format strings for enumeration types directly control the string representation of a value.</span></span> <span data-ttu-id="82f2f-226">传递给枚举值的 [ToString](xref:System.Object.ToString) 方法的格式字符串决定是使用其字符串名称（“G”和“F”格式说明符）、基础整数值（“D”格式说明符）还是十六进制值（“X”格式说明符）来显示值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-226">The format strings passed to an enumeration value’s [ToString](xref:System.Object.ToString) method determine whether the value is displayed using its string name (the "G" and "F" format specifiers), its underlying integral value (the "D" format specifier), or its hexadecimal value (the "X" format specifier).</span></span> <span data-ttu-id="82f2f-227">下面的示例演示如何使用标准格式字符串来设置 [DayOfWeek](xref:System.DayOfWeek) 枚举值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-227">The following example illustrates the use of standard format strings to format a [DayOfWeek](xref:System.DayOfWeek) enumeration value.</span></span> 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

<span data-ttu-id="82f2f-228">有关枚举格式字符串的信息，请参阅[枚举格式字符串](enumeration-format.md)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-228">For information about enumeration format strings, see [Enumeration format strings](enumeration-format.md).</span></span>

<span data-ttu-id="82f2f-229">数字类型的标准格式字符串通常定义一个结果字符串，该结果字符串的确切显示由一个或多个属性值控制。</span><span class="sxs-lookup"><span data-stu-id="82f2f-229">Standard format strings for numeric types usually define a result string whose precise appearance is controlled by one or more property values.</span></span> <span data-ttu-id="82f2f-230">例如，“C”格式说明符会将数字的格式设置为货币值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-230">For example, the "C" format specifier formats a number as a currency value.</span></span> <span data-ttu-id="82f2f-231">调用 [ToString](xref:System.Object.ToString) 方法并使用“C”格式说明符作为唯一参数时，来自当前区域性的 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象的以下属性值用于定义数字值的字符串表示形式：</span><span class="sxs-lookup"><span data-stu-id="82f2f-231">When you call the [ToString](xref:System.Object.ToString) method with the "C" format specifier as the only parameter, the following property values from the current culture’s [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object are used to define the string representation of the numeric value:</span></span>

* <span data-ttu-id="82f2f-232">[CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) 属性，指定当前区域性的货币符号。</span><span class="sxs-lookup"><span data-stu-id="82f2f-232">The [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property, which specifies the current culture’s currency symbol.</span></span>

* <span data-ttu-id="82f2f-233">[CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) 或 [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) 属性，返回用于确定以下方面的一个整数：</span><span class="sxs-lookup"><span data-stu-id="82f2f-233">The [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) or [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) property, which returns an integer that determines the following:</span></span> 

    * <span data-ttu-id="82f2f-234">货币符号的位置。</span><span class="sxs-lookup"><span data-stu-id="82f2f-234">The placement of the currency symbol.</span></span>
    
    * <span data-ttu-id="82f2f-235">负值由前导负号、尾随负号还是括号来表示。</span><span class="sxs-lookup"><span data-stu-id="82f2f-235">Whether negative values are indicated by a leading negative sign, a trailing negative sign, or parentheses.</span></span>
    
    * <span data-ttu-id="82f2f-236">在数字值和货币符号之间是否有空格。</span><span class="sxs-lookup"><span data-stu-id="82f2f-236">Whether a space appears between the numeric value and the currency symbol.</span></span>
    
* <span data-ttu-id="82f2f-237">[CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) 属性，定义结果字符串中的小数位数。</span><span class="sxs-lookup"><span data-stu-id="82f2f-237">The [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) property, which defines the number of fractional digits in the result string.</span></span>

* <span data-ttu-id="82f2f-238">[CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) 属性，定义结果字符串中的小数分隔符符号。</span><span class="sxs-lookup"><span data-stu-id="82f2f-238">The [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property, which defines the decimal separator symbol in the result string.</span></span>

* <span data-ttu-id="82f2f-239">[CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) 属性，定义组分隔符符号。</span><span class="sxs-lookup"><span data-stu-id="82f2f-239">The [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property, which defines the group separator symbol.</span></span>

* <span data-ttu-id="82f2f-240">[CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) 属性，定义小数点左边每个组的数字位数。</span><span class="sxs-lookup"><span data-stu-id="82f2f-240">The [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) property, which defines the number of digits in each group to the left of the decimal.</span></span>

* <span data-ttu-id="82f2f-241">[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) 属性，确定在未使用括号表示负值时结果字符串中使用的负号。</span><span class="sxs-lookup"><span data-stu-id="82f2f-241">The [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) property, which determines the negative sign used in the result string if parentheses are not used to indicate negative values.</span></span>

<span data-ttu-id="82f2f-242">此外，数字格式字符串可以包含一个精度说明符。</span><span class="sxs-lookup"><span data-stu-id="82f2f-242">In addition, numeric format strings may include a precision specifier.</span></span> <span data-ttu-id="82f2f-243">该说明符的含义取决于与其一起使用的格式字符串，但是，它通常指示应在结果字符串中显示的总位数或小数位数。</span><span class="sxs-lookup"><span data-stu-id="82f2f-243">The meaning of this specifier depends on the format string with which it is used, but it typically indicates either the total number of digits or the number of fractional digits that should appear in the result string.</span></span> <span data-ttu-id="82f2f-244">例如，下面的示例使用“X4”标准数字字符串和精度说明符来创建具有四个十六进制位的字符串值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-244">For example, the following example uses the "X4" standard numeric string and a precision specifier to create a string value that has four hexadecimal digits.</span></span>

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

<span data-ttu-id="82f2f-245">有关标准数字格式字符串的更多信息，请参见[标准数字格式字符串](standard-numeric.md)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-245">For more information about standard numeric formatting strings, see [Standard numeric format strings](standard-numeric.md).</span></span> 

<span data-ttu-id="82f2f-246">日期和时间值的标准格式字符串是由特定 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 属性存储的自定义格式字符串的别名。</span><span class="sxs-lookup"><span data-stu-id="82f2f-246">Standard format strings for date and time values are aliases for custom format strings stored by a particular [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) class.</span></span> <span data-ttu-id="82f2f-247">例如，如果使用“D”格式说明符调用日期和时间值的 [ToString](xref:System.Object.ToString) 方法，则使用当前区域性的 [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) 属性中存储的自定义格式字符串来显示日期和时间。</span><span class="sxs-lookup"><span data-stu-id="82f2f-247">For example, calling the [ToString](xref:System.Object.ToString) method of a date and time value with the "D" format specifier displays the date and time by using the custom format string stored in the current culture’s [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) property.</span></span> <span data-ttu-id="82f2f-248">（有关自定义格式字符串的更多信息，请参见[自定义格式字符串](#custom-format-strings)部分。）下面的示例阐释了此关系。</span><span class="sxs-lookup"><span data-stu-id="82f2f-248">(For more information about custom format strings, see the [Custom format strings](#custom-format-strings) section.) The following example illustrates this relationship.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

<span data-ttu-id="82f2f-249">有关标准日期和时间格式字符串的更多信息，请参见[标准日期和时间格式字符串](standard-datetime.md)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-249">For more information about standard date and time format strings, see [Standard date and time format strings](standard-datetime.md).</span></span>

<span data-ttu-id="82f2f-250">还可以使用标准格式字符串来定义应用程序所定义的对象的字符串表示形式，它由对象的 `ToString(String)` 方法生成。</span><span class="sxs-lookup"><span data-stu-id="82f2f-250">You can also use standard format strings to define the string representation of an application-defined object that is produced by the object’s `ToString(String)` method.</span></span> <span data-ttu-id="82f2f-251">可以定义对象支持的特定标准格式说明符，还可以决定这些格式说明符是否区分大小写。</span><span class="sxs-lookup"><span data-stu-id="82f2f-251">You can define the specific standard format specifiers that your object supports, and you can determine whether they are case-sensitive or case-insensitive.</span></span> <span data-ttu-id="82f2f-252">`ToString(String)` 方法的实现应支持下列各项：</span><span class="sxs-lookup"><span data-stu-id="82f2f-252">Your implementation of the `ToString(String)` method should support the following:</span></span>

* <span data-ttu-id="82f2f-253">一个“G”格式说明符，表示对象的常用或通用格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-253">A "G" format specifier that represents a customary or common format of the object.</span></span> <span data-ttu-id="82f2f-254">对象的 `ToString` 方法的无参数重载应调用其 `ToString(String)` 重载，并向其传递“G”标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-254">The parameterless overload of your object's `ToString` method should call its `ToString(String)` overload and pass it the "G" standard format string.</span></span>

* <span data-ttu-id="82f2f-255">支持等于空引用的格式说明符。</span><span class="sxs-lookup"><span data-stu-id="82f2f-255">Support for a format specifier that is equal to a null reference.</span></span> <span data-ttu-id="82f2f-256">应视等于空引用的格式说明符与“G”格式说明符等效。</span><span class="sxs-lookup"><span data-stu-id="82f2f-256">A format specifier that is equal to a null reference should be considered equivalent to the "G" format specifier.</span></span>

<span data-ttu-id="82f2f-257">例如，`Temperature` 类可以用摄氏度在内部存储温度，并使用格式限定符以摄氏度、华氏度和开氏度表示 `Temperature` 对象的值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-257">For example, a `Temperature` class can internally store the temperature in degrees Celsius and use format specifiers to represent the value of the `Temperature` object in degrees Celsius, degrees Fahrenheit, and kelvins.</span></span> <span data-ttu-id="82f2f-258">下面的示例进行了这方面的演示。</span><span class="sxs-lookup"><span data-stu-id="82f2f-258">The following example provides an illustration.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a><span data-ttu-id="82f2f-259">自定义格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-259">Custom format strings</span></span>

<span data-ttu-id="82f2f-260">除了标准格式字符串之外，.NET 还为数字值以及日期和时间值定义了自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-260">In addition to the standard format strings, .NET defines custom format strings for both numeric values and date and time values.</span></span> <span data-ttu-id="82f2f-261">自定义格式字符串由定义值的字符串表示形式的一个或多个自定义格式说明符组成。</span><span class="sxs-lookup"><span data-stu-id="82f2f-261">A custom format string consists of one or more custom format specifiers that define the string representation of a value.</span></span> <span data-ttu-id="82f2f-262">例如，对于 en-US 区域性，自定义日期和时间格式字符串“yyyy/mm/dd hh:mm:ss.ffff t zzz”将日期转换为“2008/11/15 07:45:00.0000 P -08:00”形式的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-262">For example, the custom date and time format string "yyyy/mm/dd hh:mm:ss.ffff t zzz" converts a date to its string representation in the form "2008/11/15 07:45:00.0000 P -08:00" for the en-US culture.</span></span> <span data-ttu-id="82f2f-263">同样，自定义格式字符串“0000”将整数值 12 转换为“0012”。</span><span class="sxs-lookup"><span data-stu-id="82f2f-263">Similarly, the custom format string "0000" converts the integer value 12 to "0012".</span></span> <span data-ttu-id="82f2f-264">有关自定义格式字符串的完整列表，请参见[自定义日期和时间格式字符串](custom-datetime.md)和[自定义数字格式字符串](custom-numeric.md)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-264">For a complete list of custom format strings, see [Custom date and time format strings](custom-datetime.md) and [Custom numeric format strings](custom-numeric.md).</span></span>

<span data-ttu-id="82f2f-265">如果格式字符串仅包含一个自定义格式说明符，则此格式说明符前面应带有百分比 (%) 符号，以免与标准格式说明符混淆。</span><span class="sxs-lookup"><span data-stu-id="82f2f-265">If a format string consists of a single custom format specifier, the format specifier should be preceded by the percent (%) symbol to avoid confusion with a standard format specifier.</span></span> <span data-ttu-id="82f2f-266">下面的示例使用“M”自定义格式说明符来显示特定日期的一位数或两位数的月份。</span><span class="sxs-lookup"><span data-stu-id="82f2f-266">The following example uses the "M" custom format specifier to display a one-digit or two-digit number of the month of a particular date.</span></span>

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

<span data-ttu-id="82f2f-267">日期和时间值的许多标准格式字符串均是由 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象的属性所定义的自定义格式字符串的别名。</span><span class="sxs-lookup"><span data-stu-id="82f2f-267">Many standard format strings for date and time values are aliases for custom format strings that are defined by properties of the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> <span data-ttu-id="82f2f-268">自定义格式字符串还为设置数字值或日期和时间值的应用程序定义格式提供了很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="82f2f-268">Custom format strings also offer considerable flexibility in providing application-defined formatting for numeric values or date and time values.</span></span> <span data-ttu-id="82f2f-269">你可以通过将多个自定义格式说明符组合成一个自定义格式字符串来为数字值以及日期和时间值定义你自己的自定义结果字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-269">You can define your own custom result strings for both numeric values and date and time values by combining multiple custom format specifiers into a single custom format string.</span></span> <span data-ttu-id="82f2f-270">下面的示例定义一个自定义格式字符串，该字符串在月份名称、日期和年份后的括号中显示星期几。</span><span class="sxs-lookup"><span data-stu-id="82f2f-270">The following example defines a custom format string that displays the day of the week in parentheses after the month name, day, and year.</span></span>

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

<span data-ttu-id="82f2f-271">以下示例定义了自定义格式字符串，其中 [Int64](xref:System.Int64) 值显示为标准的美国七位数电话号码及其区号。</span><span class="sxs-lookup"><span data-stu-id="82f2f-271">The following example defines a custom format string that displays an [Int64](xref:System.Int64) value as a standard, seven-digit U.S. telephone number along with its area code.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

<span data-ttu-id="82f2f-272">尽管标准格式字符串一般可以满足应用程序定义的类型的大多数格式设置需求，但你还可以定义自定义格式说明符来设置类型的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-272">Although standard format strings can generally handle most of the formatting needs for your application-defined types, you may also define custom format specifiers to format your types.</span></span> 

### <a name="format-strings-and-net-types"></a><span data-ttu-id="82f2f-273">格式字符串和 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="82f2f-273">Format strings and .NET types</span></span>

<span data-ttu-id="82f2f-274">所有数字类型（即 [Byte](xref:System.Byte)、[Decimal](xref:System.Decimal)、[Double](xref:System.Double)、[Int16](xref:System.Int16)、[Int32](xref:System.Int32)、[Int64](xref:System.Int64)、[SByte](xref:System.SByte)、[Single](xref:System.Single)、[UInt16](xref:System.UInt16)、[UInt32](xref:System.UInt32)、[UInt64](xref:System.UInt64) 和 [BigInteger](xref:System.Numerics.BigInteger) 类型），以及 [DateTime](xref:System.DateTime)、[DateTimeOffset](xref:System.DateTimeOffset)、[TimeSpan](xref:System.TimeSpan)、[Guid](xref:System.Guid) 和所有枚举类型都支持使用格式字符串设置格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-274">All numeric types (that is, the [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), and [BigInteger](xref:System.Numerics.BigInteger) types), as well as the [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid), and all enumeration types, support formatting with format strings.</span></span> <span data-ttu-id="82f2f-275">有关各类型支持的特定格式字符串的信息，请参见下列主题：</span><span class="sxs-lookup"><span data-stu-id="82f2f-275">For information on the specific format strings supported by each type, see the following topics:</span></span> 

<span data-ttu-id="82f2f-276">标题</span><span class="sxs-lookup"><span data-stu-id="82f2f-276">Title</span></span> | <span data-ttu-id="82f2f-277">定义</span><span class="sxs-lookup"><span data-stu-id="82f2f-277">Definition</span></span>
----- | ----------
[<span data-ttu-id="82f2f-278">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-278">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="82f2f-279">描述用于创建数字值的常用字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-279">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="82f2f-280">自定义数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-280">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="82f2f-281">描述用于创建数字值的应用程序特定格式的自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-281">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="82f2f-282">标准日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-282">Standard date and time format strings</span></span>](standard-datetime.md) | <span data-ttu-id="82f2f-283">描述用于创建 [DateTime](xref:System.DateTime) 值的常用字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-283">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="82f2f-284">自定义日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-284">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="82f2f-285">描述用于创建 [DateTime](xref:System.DateTime) 值的应用程序特定格式的自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-285">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="82f2f-286">标准 TimeSpan 格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-286">Standard TimeSpan format Strings</span></span>](standard-timespan.md) | <span data-ttu-id="82f2f-287">描述用于创建时间间隔的常用字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-287">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="82f2f-288">自定义的 TimeSpan 格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-288">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="82f2f-289">描述用于创建时间间隔的应用程序特定格式的自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-289">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="82f2f-290">枚举格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-290">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="82f2f-291">描述用于创建枚举值的字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-291">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
<span data-ttu-id="82f2f-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span><span class="sxs-lookup"><span data-stu-id="82f2f-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span></span> | <span data-ttu-id="82f2f-293">描述 [Guid](xref:System.Guid) 值的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-293">Describes standard format strings for [Guid](xref:System.Guid) values.</span></span>

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a><span data-ttu-id="82f2f-294">使用格式提供程序和 IFormatProvider 接口的区分区域性的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-294">Culture-Sensitive Formatting with Format Providers and the IFormatProvider Interface</span></span>

<span data-ttu-id="82f2f-295">尽管格式说明符允许你自定义对象的格式设置，但是生成有意义的对象字符串表示形式通常需要附加格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="82f2f-295">Although format specifiers let you customize the formatting of objects, producing a meaningful string representation of objects often requires additional formatting information.</span></span> <span data-ttu-id="82f2f-296">例如，通过使用“C”标准格式字符串或自定义格式字符串（如“$ #,#.00”）来将数字格式设置为货币值至少需要提供有关正确的货币符号、组分隔符和小数点分隔符的信息，以便包括在带有格式的字符串中。</span><span class="sxs-lookup"><span data-stu-id="82f2f-296">For example, formatting a number as a currency value by using either the "C" standard format string or a custom format string such as "$ #,#.00" requires, at a minimum, information about the correct currency symbol, group separator, and decimal separator to be available to include in the formatted string.</span></span> <span data-ttu-id="82f2f-297">在 .NET 中，此附加格式设置信息通过 [IFormatProvider](xref:System.IFormatProvider) 接口来提供，该接口作为数字类型以及日期和时间类型的 `ToString` 方法的一个或多个重载的参数提供。</span><span class="sxs-lookup"><span data-stu-id="82f2f-297">In .NET, this additional formatting information is made available through the [IFormatProvider](xref:System.IFormatProvider) interface, which is provided as a parameter to one or more overloads of the `ToString` method of numeric types and date and time types.</span></span> <span data-ttu-id="82f2f-298">[IFormatProvider](xref:System.IFormatProvider) 实现在 .NET Framework 中用于支持区域性特定的格式设置。</span><span class="sxs-lookup"><span data-stu-id="82f2f-298">[IFormatProvider](xref:System.IFormatProvider) implementations are used in .NET to support culture-specific formatting.</span></span> <span data-ttu-id="82f2f-299">下面的示例演示在使用三个代表不同区域的 [IFormatProvider](xref:System.IFormatProvider) 对象设置某个对象的格式时，该对象的字符串表示形式将如何变化。</span><span class="sxs-lookup"><span data-stu-id="82f2f-299">The following example illustrates how the string representation of an object changes when it is formatted with three [IFormatProvider](xref:System.IFormatProvider) objects that represent different cultures.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

<span data-ttu-id="82f2f-300">[IFormatProvider](xref:System.IFormatProvider) 接口包含一个 [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)) 方法，该方法只有一个参数，该参数指定提供格式设置信息的对象类型。</span><span class="sxs-lookup"><span data-stu-id="82f2f-300">The [IFormatProvider](xref:System.IFormatProvider) interface includes one method, [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), which has a single parameter that specifies the type of object that provides formatting information.</span></span> <span data-ttu-id="82f2f-301">如果该方法可以提供该类型的对象，则返回它。</span><span class="sxs-lookup"><span data-stu-id="82f2f-301">If the method can provide an object of that type, it returns it.</span></span> <span data-ttu-id="82f2f-302">否则，它返回空引用。</span><span class="sxs-lookup"><span data-stu-id="82f2f-302">Otherwise, it returns a null reference.</span></span>

<span data-ttu-id="82f2f-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 是回调方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) is a callback method.</span></span> <span data-ttu-id="82f2f-304">调用包含 [IFormatProvider](xref:System.IFormatProvider) 参数的 `ToString` 方法重载时，它会调用该 [IFormatProvider](xref:System.IFormatProvider) 对象的 [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-304">When you call a `ToString` method overload that includes an [IFormatProvider](xref:System.IFormatProvider) parameter, it calls the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method of that [IFormatProvider](xref:System.IFormatProvider) object.</span></span> <span data-ttu-id="82f2f-305">[GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 方法负责将提供所需格式设置信息（就像 *formatType* 参数指定的一样）的对象返回给 `ToString` 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-305">The [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method is responsible for returning an object that provides the necessary formatting information, as specified by its *formatType* parameter, to the `ToString` method.</span></span> 

<span data-ttu-id="82f2f-306">一些格式设置或字符串转换方法包含 [IFormatProvider](xref:System.IFormatProvider) 类型的参数，但是很多情况下在调用该方法时将忽略该参数的值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-306">A number of formatting or string conversion methods include a parameter of type [IFormatProvider](xref:System.IFormatProvider), but in many cases the value of the parameter is ignored when the method is called.</span></span> <span data-ttu-id="82f2f-307">下表列出了使用 [Type](xref:System.Type) 对象的参数和类型的一些格式设置方法，该对象传递给 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-307">The following table lists some of the formatting methods that use the parameter and the type of the [Type](xref:System.Type) object that they pass to the [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method.</span></span> 

<span data-ttu-id="82f2f-308">方法</span><span class="sxs-lookup"><span data-stu-id="82f2f-308">Method</span></span> | <span data-ttu-id="82f2f-309">formatType 参数的类型</span><span class="sxs-lookup"><span data-stu-id="82f2f-309">Type of *formatType* parameter</span></span>
------ | ------------------------------
<span data-ttu-id="82f2f-310">数字类型的 `ToString` 方法</span><span class="sxs-lookup"><span data-stu-id="82f2f-310">`ToString` method of numeric types</span></span> | [<span data-ttu-id="82f2f-311">System.Globalization.NumberFormatInfo</span><span class="sxs-lookup"><span data-stu-id="82f2f-311">System.Globalization.NumberFormatInfo</span></span>](xref:System.Globalization.NumberFormatInfo)
<span data-ttu-id="82f2f-312">日期和时间类型的 `ToString` 方法</span><span class="sxs-lookup"><span data-stu-id="82f2f-312">`ToString` method of date and time types</span></span> | [<span data-ttu-id="82f2f-313">System.Globalization.DateTimeFormatInfo</span><span class="sxs-lookup"><span data-stu-id="82f2f-313">System.Globalization.DateTimeFormatInfo</span></span>](xref:System.Globalization.DateTimeFormatInfo)
<span data-ttu-id="82f2f-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="82f2f-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="82f2f-315">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="82f2f-315">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)
<span data-ttu-id="82f2f-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="82f2f-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="82f2f-317">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="82f2f-317">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

<span data-ttu-id="82f2f-318">.NET 提供了实现 [IFormatProvider](xref:System.IFormatProvider) 的三个类：</span><span class="sxs-lookup"><span data-stu-id="82f2f-318">.NET provides three classes that implement [IFormatProvider](xref:System.IFormatProvider):</span></span> 

* <span data-ttu-id="82f2f-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 类，提供特定区域性的日期和时间值的格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="82f2f-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), a class that provides formatting information for date and time values for a specific culture.</span></span> <span data-ttu-id="82f2f-320">其 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 实现返回它自身的实例。</span><span class="sxs-lookup"><span data-stu-id="82f2f-320">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="82f2f-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 类，提供特定区域性的数字格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="82f2f-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), a class that provides numeric formatting information for a specific culture.</span></span> <span data-ttu-id="82f2f-322">其 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 实现返回它自身的实例。</span><span class="sxs-lookup"><span data-stu-id="82f2f-322">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="82f2f-323">[CultureInfo](xref:System.Globalization.CultureInfo)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span></span> <span data-ttu-id="82f2f-324">其 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 实现可以返回一个 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象（可提供数字格式设置信息）或一个 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象（可提供日期和时间值的格式设置信息）。</span><span class="sxs-lookup"><span data-stu-id="82f2f-324">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation can return either a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to provide numeric formatting information or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object to provide formatting information for date and time values.</span></span> 

<span data-ttu-id="82f2f-325">你还可以实现自己的格式提供程序来替换上述任意一个类。</span><span class="sxs-lookup"><span data-stu-id="82f2f-325">You can also implement your own format provider to replace any one of these classes.</span></span> <span data-ttu-id="82f2f-326">但是，如果你的实现的 `GetFormat` 方法必须向 `ToString` 方法提供格式设置信息，则它必须返回上表中列出的相应类型的对象。</span><span class="sxs-lookup"><span data-stu-id="82f2f-326">However, your implementation’s `GetFormat` method must return an object of the type listed in the previous table if it has to provide formatting information to the `ToString` method.</span></span>

### <a name="culture-sensitive-formatting-of-numeric-values"></a><span data-ttu-id="82f2f-327">数值的区分区域性的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-327">Culture-sensitive formatting of numeric values</span></span>

<span data-ttu-id="82f2f-328">默认情况下，数值的格式设置是区分区域性的。</span><span class="sxs-lookup"><span data-stu-id="82f2f-328">By default, the formatting of numeric values is culture-sensitive.</span></span> <span data-ttu-id="82f2f-329">如果在调用格式设置方法时不指定区域性，则将使用当前线程区域性的格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-329">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="82f2f-330">下面的示例演示了这一点，其中对当前线程区域性进行了四次更改，随后调用了 [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-330">This is illustrated in the following example, which changes the current thread culture four times and then calls the [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) method.</span></span> <span data-ttu-id="82f2f-331">每次更改后，结果字符串均反映当前区域性的格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-331">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="82f2f-332">这是因为 `ToString` 和 `ToString(String)` 方法会包装对每个数值类型的 `ToString(String, IFormatProvider)` 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="82f2f-332">This is because the `ToString` and `ToString(String)` methods wrap calls to each numeric type's `ToString(String, IFormatProvider)` method.</span></span> 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

<span data-ttu-id="82f2f-333">你还可以设置特定区域性数值的格式，方法是调用具有 provider 参数的 `ToString` 重载，并将其作为以下对象之一的参数进行传递：</span><span class="sxs-lookup"><span data-stu-id="82f2f-333">You can also format a numeric value for a specific culture by calling a `ToString` overload that has a *provider* parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="82f2f-334">一个 [CultureInfo](xref:System.Globalization.CultureInfo) 对象，此对象代表要使用其格式设置约定的区域性。</span><span class="sxs-lookup"><span data-stu-id="82f2f-334">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="82f2f-335">它的 [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) 方法会返回 [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) 属性的值，即提供数字区域性特定格式设置信息的 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="82f2f-335">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="82f2f-336">一个 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象，此对象用于定义要使用的区域性特定格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-336">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="82f2f-337">它的 [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) 方法会返回它自身的一个实例。</span><span class="sxs-lookup"><span data-stu-id="82f2f-337">Its [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="82f2f-338">下面的示例使用了表示英语（美国）和英语（英国）区域性以及法语和俄罗斯语非特定区域性的 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象，来设置浮点数字的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-338">The following example uses [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a floating-point number.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a><span data-ttu-id="82f2f-339">日期和时间值的区分区域性的格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-339">Culture-sensitive formatting of date and time values</span></span>

<span data-ttu-id="82f2f-340">默认情况下，日期和时间值的格式设置是区分区域性的。</span><span class="sxs-lookup"><span data-stu-id="82f2f-340">By default, the formatting of date and time values is culture-sensitive.</span></span> <span data-ttu-id="82f2f-341">如果在调用格式设置方法时不指定区域性，则将使用当前线程区域性的格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-341">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="82f2f-342">下面的示例演示了这一点，其中对当前线程区域性进行了四次更改，随后调用了 [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-342">This is illustrated in the following example, which changes the current thread culture four times and then calls the [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) method.</span></span> <span data-ttu-id="82f2f-343">每次更改后，结果字符串均反映当前区域性的格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-343">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="82f2f-344">这是因为 [DateTime.ToString()](xref:System.DateTime.ToString)、[DateTime.ToString(String)](xref:System.DateTime.ToString(System.String))、[DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) 和 [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) 方法会包装对 [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) 和 [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="82f2f-344">This is because the [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)), and [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) methods wrap calls to the [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) methods.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

<span data-ttu-id="82f2f-345">你还可以设置特定区域性日期和时间值的格式，方法是调用具有 provider 参数的 [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) 或 [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) 重载，并将其作为以下对象之一的参数进行传递：</span><span class="sxs-lookup"><span data-stu-id="82f2f-345">You can also format a date and time value for a specific culture by calling a [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) overload that has a provider parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="82f2f-346">一个 [CultureInfo](xref:System.Globalization.CultureInfo) 对象，此对象代表要使用其格式设置约定的区域性。</span><span class="sxs-lookup"><span data-stu-id="82f2f-346">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="82f2f-347">它的 [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) 方法会返回 [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) 属性的值，即提供数字区域性特定格式设置信息的 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="82f2f-347">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="82f2f-348">一个 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象，此对象用于定义要使用的区域性特定格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="82f2f-348">A [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="82f2f-349">它的 [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) 方法会返回它自身的一个实例。</span><span class="sxs-lookup"><span data-stu-id="82f2f-349">Its [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="82f2f-350">下面的示例使用了表示英语（美国）和英语（英国）区域性以及法语和俄罗斯语非特定区域性的 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象，来设置日期的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-350">The following example uses [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a date.</span></span> 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a><span data-ttu-id="82f2f-351">IFormattable 接口</span><span class="sxs-lookup"><span data-stu-id="82f2f-351">The IFormattable interface</span></span>

<span data-ttu-id="82f2f-352">通常，使用格式字符串和一个 [IFormatProvider](xref:System.IFormatProvider) 参数来重载 `ToString` 方法的类型还实现 [IFormattable](xref:System.IFormattable) 接口。</span><span class="sxs-lookup"><span data-stu-id="82f2f-352">Typically, types that overload the `ToString` method with a format string and an [IFormatProvider](xref:System.IFormatProvider) parameter also implement the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="82f2f-353">此接口具有一个成员 [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider))，该成员同时将格式字符串和格式提供程序作为参数。</span><span class="sxs-lookup"><span data-stu-id="82f2f-353">This interface has a single member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), that includes both a format string and a format provider as parameters.</span></span>

<span data-ttu-id="82f2f-354">对应用程序定义的类实现 [IFormattable](xref:System.IFormattable) 接口具有两大优势：</span><span class="sxs-lookup"><span data-stu-id="82f2f-354">Implementing the [IFormattable](xref:System.IFormattable) interface for your application-defined class offers two advantages:</span></span> 

* <span data-ttu-id="82f2f-355">支持使用 [Convert](xref:System.Convert) 类进行字符串转换。</span><span class="sxs-lookup"><span data-stu-id="82f2f-355">Support for string conversion by the [Convert](xref:System.Convert) class.</span></span> <span data-ttu-id="82f2f-356">调用 [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) 和 [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) 方法会自动调用 [IFormattable](xref:System.IFormattable) 实现。</span><span class="sxs-lookup"><span data-stu-id="82f2f-356">Calls to the [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) and [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) methods call your [IFormattable](xref:System.IFormattable) implementation automatically.</span></span>

* <span data-ttu-id="82f2f-357">支持复合格式设置。</span><span class="sxs-lookup"><span data-stu-id="82f2f-357">Support for composite formatting.</span></span> <span data-ttu-id="82f2f-358">如果使用包含格式字符串的格式项设置自定义类型的格式，则公共语言运行时自动调用 [IFormattable](xref:System.IFormattable) 实现，并向其传递该格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-358">If a format item that includes a format string is used to format your custom type, the Common Language Runtime automatically calls your [IFormattable](xref:System.IFormattable) implementation and passes it the format string.</span></span> <span data-ttu-id="82f2f-359">有关采用 `String.Format` 或 `Console.WriteLine` 等方法进行复合格式设置的更多信息，请参见[复合格式设置](#composite-formatting)部分。</span><span class="sxs-lookup"><span data-stu-id="82f2f-359">For more information about composite formatting with methods such as `String.Format` or `Console.WriteLine`, see the [Composite formatting](#composite-formatting) section.</span></span>

<span data-ttu-id="82f2f-360">下面的示例定义一个实现 [IFormattable](xref:System.IFormattable) 接口的 `Temperature` 类。</span><span class="sxs-lookup"><span data-stu-id="82f2f-360">The following example defines a `Temperature` class that implements the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="82f2f-361">它支持“C”或“G”格式说明符（用于以摄氏度显示温度）、“F”格式说明符（用于以华氏度显示温度）和“K”格式说明符（用于以开氏度显示温度）。</span><span class="sxs-lookup"><span data-stu-id="82f2f-361">It supports the "C" or "G" format specifiers to display the temperature in Celsius, the "F" format specifier to display the temperature in Fahrenheit, and the "K" format specifier to display the temperature in Kelvin.</span></span>

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

<span data-ttu-id="82f2f-362">下面的示例实例化一个 `Temperature` 对象。</span><span class="sxs-lookup"><span data-stu-id="82f2f-362">The following example instantiates a `Temperature` object.</span></span> <span data-ttu-id="82f2f-363">然后，它调用 [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) 方法，并使用多个复合格式字符串获取 `Temperature` 对象的不同字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-363">It then calls the [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) method and uses several composite format strings to obtain different string representations of a `Temperature` object.</span></span> <span data-ttu-id="82f2f-364">其中每一个方法调用都依次调用 `Temperature` 类的 [IFormattable](xref:System.IFormattable) 实现。</span><span class="sxs-lookup"><span data-stu-id="82f2f-364">Each of these method calls, in turn, calls the [IFormattable](xref:System.IFormattable) implementation of the `Temperature` class.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a><span data-ttu-id="82f2f-365">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-365">Composite formatting</span></span>

<span data-ttu-id="82f2f-366">一些方法（如 `String.Format` 和 `StringBuilder.AppendFormat`）支持复合格式设置。</span><span class="sxs-lookup"><span data-stu-id="82f2f-366">Some methods, such as `String.Format` and `StringBuilder.AppendFormat`, support composite formatting.</span></span> <span data-ttu-id="82f2f-367">复合格式字符串是一种模板，该模板返回合并了零个、一个或多个对象的字符串表示形式的单一字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-367">A composite format string is a kind of template that returns a single string that incorporates the string representation of zero, one, or more objects.</span></span> <span data-ttu-id="82f2f-368">每个对象均由复合格式字符串中的索引格式项表示。</span><span class="sxs-lookup"><span data-stu-id="82f2f-368">Each object is represented in the composite format string by an indexed format item.</span></span> <span data-ttu-id="82f2f-369">格式项的索引对应于格式项在方法的参数列表中所表示的对象位置。</span><span class="sxs-lookup"><span data-stu-id="82f2f-369">The index of the format item corresponds to the position of the object that it represents in the method's parameter list.</span></span> <span data-ttu-id="82f2f-370">索引是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="82f2f-370">Indexes are zero-based.</span></span> <span data-ttu-id="82f2f-371">例如，在以下对 `String.Format` 方法的调用中，第一个格式项 `{0:D}` 被 `thatDate` 的字符串表示形式；第二个格式项 `{1}` 被 `item1` 的字符串表示形式替换；第三个格式项 `{2:C2}` 被 `item1.Value` 的字符串表示形式替换。</span><span class="sxs-lookup"><span data-stu-id="82f2f-371">For example, in the following call to the `String.Format` method, the first format item, `{0:D}`, is replaced by the string representation of `thatDate`; the second format item, `{1}`, is replaced by the string representation of `item1`; and the third format item, `{2:C2}`, is replaced by the string representation of `item1.Value`.</span></span>

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

<span data-ttu-id="82f2f-372">除了将格式项替换为其相应对象的字符串表示形式之外，格式项还可让你控制：</span><span class="sxs-lookup"><span data-stu-id="82f2f-372">In addition to replacing a format item with the string representation of its corresponding object, format items also let you control the following:</span></span> 

* <span data-ttu-id="82f2f-373">将对象表示为字符串的特定方法（如果对象实现 [IFormattable](xref:System.IFormattable) 接口并支持格式字符串）。</span><span class="sxs-lookup"><span data-stu-id="82f2f-373">The specific way in which an object is represented as a string, if the object implements the [IFormattable](xref:System.IFormattable) interface and supports format strings.</span></span> <span data-ttu-id="82f2f-374">为此，可在格式项的索引后加上 :（冒号），后跟一个有效的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-374">You do this by following the format item's index with a : (colon) followed by a valid format string.</span></span> <span data-ttu-id="82f2f-375">前面的示例执行此操作的方式是：格式化带有“d”（短日期模式）格式字符串（例如，`{0:d}`）的日期值，并格式化带有“C2”格式字符串（例如，`{2:C2}` 的数值，将数量表示为具有两位小数位数的货币值）。</span><span class="sxs-lookup"><span data-stu-id="82f2f-375">The previous example did this by formatting a date value with the "d" (short date pattern) format string (for example, `{0:d}`) and by formatting a numeric value with the "C2" format string (for example, `{2:C2}` to represent the number as a currency value with two fractional decimal digits).</span></span> 

* <span data-ttu-id="82f2f-376">包含对象的字符串表示形式的字段的宽度以及该字段中字符串表现形式的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-376">The width of the field that contains the object's string representation, and the alignment of the string representation in that field.</span></span> <span data-ttu-id="82f2f-377">为此，可在格式项的索引后加上 ,（逗号），后跟字段宽度。</span><span class="sxs-lookup"><span data-stu-id="82f2f-377">You do this by following the format item's index with a , (comma) followed the field width.</span></span> <span data-ttu-id="82f2f-378">如果字段宽度为正值，则字段中的字符串为右对齐，如果字段宽度是负值，则为左对齐。</span><span class="sxs-lookup"><span data-stu-id="82f2f-378">The string is right-aligned in the field if the field width is a positive value, and it is left-aligned if the field width is a negative value.</span></span> <span data-ttu-id="82f2f-379">在下面的示例中，在由 20 个字符组成的字段中的日期值左对齐，而在由 11 个字符组成的字段中，带有一位小数的十进制值右对齐。</span><span class="sxs-lookup"><span data-stu-id="82f2f-379">The following example left-aligns date values in a 20-character field, and it right-aligns decimal values with one fractional digit in an 11-character field.</span></span> 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

<span data-ttu-id="82f2f-380">请注意，如果对齐字符串组件和格式字符串组件均存在，则前者位于后者之前（例如，`{0,-20:g}`）。</span><span class="sxs-lookup"><span data-stu-id="82f2f-380">Note that, if both the alignment string component and the format string component are present, the former precedes the latter (for example, `{0,-20:g}`.</span></span> 

<span data-ttu-id="82f2f-381">有关复合格式设置的更多信息，请参见[复合格式设置](composite-format.md)。</span><span class="sxs-lookup"><span data-stu-id="82f2f-381">For more information about composite formatting, see [Composite formatting](composite-format.md).</span></span>

## <a name="custom-formatting-with-icustomformatter"></a><span data-ttu-id="82f2f-382">使用 ICustomFormatter 进行自定义格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-382">Custom formatting with ICustomFormatter</span></span>

<span data-ttu-id="82f2f-383">两种复合格式设置方法（[String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) 和 [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))）包括一个支持自定义格式设置的格式提供程序参数。</span><span class="sxs-lookup"><span data-stu-id="82f2f-383">Two composite formatting methods, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) and [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), include a format provider parameter that supports custom formatting.</span></span> <span data-ttu-id="82f2f-384">当调用其中一种格式设置方法时，该方法会将表示 [ICustomFormatter](xref:System.ICustomFormatter) 接口的 [Type](xref:System.Type) 对象传递到格式提供程序的 `GetFormat` 方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-384">When either of these formatting methods is called, it passes a [Type](xref:System.Type) object that represents an [ICustomFormatter](xref:System.ICustomFormatter) interface to the format provider’s `GetFormat` method.</span></span> <span data-ttu-id="82f2f-385">`GetFormat` 方法然后负责返回提供自定义格式设置功能的 [ICustomFormatter](xref:System.ICustomFormatter) 实现。</span><span class="sxs-lookup"><span data-stu-id="82f2f-385">The `GetFormat` method is then responsible for returning the [ICustomFormatter](xref:System.ICustomFormatter) implementation that provides custom formatting.</span></span>

<span data-ttu-id="82f2f-386">[ICustomFormatter](xref:System.ICustomFormatter) 接口具有一个方法 [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))，复合格式设置方法为复合格式字符串中的每一格式项自动调用一次该方法。</span><span class="sxs-lookup"><span data-stu-id="82f2f-386">The [ICustomFormatter](xref:System.ICustomFormatter) interface has a single method, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), that is called automatically by a composite formatting method, once for each format item in a composite format string.</span></span> <span data-ttu-id="82f2f-387">[Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 方法具有三个参数：一个格式字符串（表示格式项中的 formatString 参数）、一个要设置格式的对象和一个提供格式设置服务的 [IFormatProvider](xref:System.IFormatProvider) 对象。</span><span class="sxs-lookup"><span data-stu-id="82f2f-387">The [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method has three parameters: a format string, which represents the *formatString* argument in a format item, an object to format, and an [IFormatProvider](xref:System.IFormatProvider) object that provides formatting services.</span></span> <span data-ttu-id="82f2f-388">通常，实现 [ICustomFormatter](xref:System.ICustomFormatter) 的类还会实现 [IFormatProvider](xref:System.IFormatProvider)，因此上述最后一个参数是对自定义格式设置类自身的引用。</span><span class="sxs-lookup"><span data-stu-id="82f2f-388">Typically, the class that implements [ICustomFormatter](xref:System.ICustomFormatter) also implements [IFormatProvider](xref:System.IFormatProvider), so this last parameter is a reference to the custom formatting class itself.</span></span> <span data-ttu-id="82f2f-389">该方法返回要设置格式的对象的带格式自定义字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-389">The method returns a custom formatted string representation of the object to be formatted.</span></span> <span data-ttu-id="82f2f-390">如果该方法无法设置对象的格式，则应返回空引用。</span><span class="sxs-lookup"><span data-stu-id="82f2f-390">If the method cannot format the object, it should return a null reference.</span></span>

<span data-ttu-id="82f2f-391">下面的示例提供一个名为 `ByteByByteFormatter` 的 [ICustomFormatter](xref:System.ICustomFormatter) 实现，该实现将整数值显示为两位的十六进制值后跟一个空格的序列。</span><span class="sxs-lookup"><span data-stu-id="82f2f-391">The following example provides an [ICustomFormatter](xref:System.ICustomFormatter) implementation named `ByteByByteFormatter` that displays integer values as a sequence of two-digit hexadecimal values followed by a space.</span></span>

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

<span data-ttu-id="82f2f-392">下面的示例使用 `ByteByByteFormatter` 类设置整数值的格式。</span><span class="sxs-lookup"><span data-stu-id="82f2f-392">The following example uses the `ByteByByteFormatter` class to format integer values.</span></span> <span data-ttu-id="82f2f-393">请注意，在第二个 [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 方法调用中多次调用了 [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 方法，并在第三个方法调用中使用了默认 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 提供程序，这是因为 .`.ByteByByteFormatter.Format` 方法无法识别“N0”格式字符串并返回空引用。</span><span class="sxs-lookup"><span data-stu-id="82f2f-393">Note that the [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method is called more than once in the second [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method call, and that the default [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) provider is used in the third method call because the `.ByteByByteFormatter.Format` method does not recognize the "N0" format string and returns a null reference.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a><span data-ttu-id="82f2f-394">相关主题</span><span class="sxs-lookup"><span data-stu-id="82f2f-394">Related topics</span></span>

<span data-ttu-id="82f2f-395">标题</span><span class="sxs-lookup"><span data-stu-id="82f2f-395">Title</span></span> | <span data-ttu-id="82f2f-396">定义</span><span class="sxs-lookup"><span data-stu-id="82f2f-396">Definition</span></span>
----- | ----------
[<span data-ttu-id="82f2f-397">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-397">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="82f2f-398">描述用于创建数字值的常用字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-398">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="82f2f-399">自定义数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-399">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="82f2f-400">描述用于创建数字值的应用程序特定格式的自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-400">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="82f2f-401">标准日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-401">Standard date and time format strings</span></span>](standard-datetime.md) |  <span data-ttu-id="82f2f-402">描述用于创建 [DateTime](xref:System.DateTime) 值的常用字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-402">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="82f2f-403">自定义日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-403">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="82f2f-404">描述用于创建 [DateTime](xref:System.DateTime) 值的应用程序特定格式的自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-404">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="82f2f-405">标准 TimeSpan 格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-405">Standard TimeSpan format strings</span></span>](standard-timespan.md) | <span data-ttu-id="82f2f-406">描述用于创建时间间隔的常用字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-406">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="82f2f-407">自定义的 TimeSpan 格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-407">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="82f2f-408">描述用于创建时间间隔的应用程序特定格式的自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-408">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="82f2f-409">枚举格式字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-409">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="82f2f-410">描述用于创建枚举值的字符串表示形式的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-410">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
[<span data-ttu-id="82f2f-411">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="82f2f-411">Composite formatting</span></span>](composite-format.md) | <span data-ttu-id="82f2f-412">描述如何将一个或多个设置了格式的值嵌入字符串。</span><span class="sxs-lookup"><span data-stu-id="82f2f-412">Describes how to embed one or more formatted values in a string.</span></span> <span data-ttu-id="82f2f-413">然后该字符串可以显示在控制台上或被写至流。</span><span class="sxs-lookup"><span data-stu-id="82f2f-413">The string can subsequently be displayed on the console or written to a stream.</span></span>
[<span data-ttu-id="82f2f-414">执行格式设置操作</span><span class="sxs-lookup"><span data-stu-id="82f2f-414">Performing formatting operations</span></span>](performing-formatting-operations.md) | <span data-ttu-id="82f2f-415">列出分步说明如何执行特定的格式设置操作的主题。</span><span class="sxs-lookup"><span data-stu-id="82f2f-415">Lists topics that provide step-by-step instructions for performing specific formatting operations.</span></span>
[<span data-ttu-id="82f2f-416">分析字符串</span><span class="sxs-lookup"><span data-stu-id="82f2f-416">Parsing strings</span></span>](parsing-strings.md) | <span data-ttu-id="82f2f-417">描述如何将对象初始化为这些对象的字符串表示形式所描述的值。</span><span class="sxs-lookup"><span data-stu-id="82f2f-417">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="82f2f-418">分析是格式化的反向操作。</span><span class="sxs-lookup"><span data-stu-id="82f2f-418">Parsing is the inverse operation of formatting.</span></span>

## <a name="reference"></a><span data-ttu-id="82f2f-419">参考</span><span class="sxs-lookup"><span data-stu-id="82f2f-419">Reference</span></span>

[<span data-ttu-id="82f2f-420">System.IFormattable</span><span class="sxs-lookup"><span data-stu-id="82f2f-420">System.IFormattable</span></span>](xref:System.IFormattable)

[<span data-ttu-id="82f2f-421">System.IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="82f2f-421">System.IFormatProvider</span></span>](xref:System.IFormatProvider)

[<span data-ttu-id="82f2f-422">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="82f2f-422">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

