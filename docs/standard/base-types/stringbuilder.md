---
title: "使用 StringBuilder 类"
description: "使用 StringBuilder 类"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 076e10e095b50cc96187f2ec13ade2365d83dad3
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="using-the-stringbuilder-class"></a><span data-ttu-id="c1673-104">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="c1673-104">Using the StringBuilder class</span></span>

<span data-ttu-id="c1673-105">[String](xref:System.String) 对象是不可变的。</span><span class="sxs-lookup"><span data-stu-id="c1673-105">The [String](xref:System.String) object is immutable.</span></span> <span data-ttu-id="c1673-106">每次使用 [System.String](xref:System.String) 类中的一个方法时，都要在内存中创建一个新的字符串对象，这就需要为该新对象分配新的空间。</span><span class="sxs-lookup"><span data-stu-id="c1673-106">Every time you use one of the methods in the [System.String](xref:System.String) class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="c1673-107">在需要对字符串执行重复修改的情况下，与创建新 [String](xref:System.String) 对象关联的开销可能非常大。</span><span class="sxs-lookup"><span data-stu-id="c1673-107">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new [String](xref:System.String) object can be costly.</span></span> <span data-ttu-id="c1673-108">如果要修改字符串而不创建新的对象，则可以使用 [System.Text.StringBuilder](xref:System.Text.StringBuilder) 类。</span><span class="sxs-lookup"><span data-stu-id="c1673-108">The [System.Text.StringBuilder](xref:System.Text.StringBuilder) class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="c1673-109">例如，在一次循环中将许多字符串连接在一起时，使用 [StringBuilder](xref:System.Text.StringBuilder) 类可以提升性能。</span><span class="sxs-lookup"><span data-stu-id="c1673-109">For example, using the [StringBuilder](xref:System.Text.StringBuilder) class can boost performance when concatenating many strings together in a loop.</span></span>

## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="c1673-110">导入 System.Text 命名空间</span><span class="sxs-lookup"><span data-stu-id="c1673-110">Importing the System.Text Namespace</span></span>

<span data-ttu-id="c1673-111">[StringBuilder](xref:System.Text.StringBuilder) 类位于 [System.Text](xref:System.Text) 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c1673-111">The [StringBuilder](xref:System.Text.StringBuilder) class is found in the [System.Text](xref:System.Text) namespace.</span></span> <span data-ttu-id="c1673-112">为了避免必须在代码中提供完全限定的类型名称，可以导入 [System.Text](xref:System.Text) 命名空间：</span><span class="sxs-lookup"><span data-stu-id="c1673-112">To avoid having to provide a fully qualified type name in your code, you can import the [System.Text](xref:System.Text) namespace:</span></span> 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="c1673-113">实例化 StringBuilder 对象</span><span class="sxs-lookup"><span data-stu-id="c1673-113">Instantiating a StringBuilder Object</span></span>

<span data-ttu-id="c1673-114">通过利用其中一个重载的构造函数方法初始化变量，可以创建 [StringBuilder](xref:System.Text.StringBuilder) 类的新实例，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c1673-114">You can create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="c1673-115">设置容量和长度</span><span class="sxs-lookup"><span data-stu-id="c1673-115">Setting the Capacity and Length</span></span>

<span data-ttu-id="c1673-116">虽然 [StringBuilder](xref:System.Text.StringBuilder) 是动态对象，允许增加其所封装字符串中的字符数，但也可以指定该对象可保留的最大字符数的值。</span><span class="sxs-lookup"><span data-stu-id="c1673-116">Although the [StringBuilder](xref:System.Text.StringBuilder) is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="c1673-117">此值称为该对象的容量，切勿将它与当前 [StringBuilder](xref:System.Text.StringBuilder) 所保留的字符串长度相混淆。</span><span class="sxs-lookup"><span data-stu-id="c1673-117">This value is called the capacity of the object and should not be confused with the length of the string that the current [StringBuilder](xref:System.Text.StringBuilder) holds.</span></span> <span data-ttu-id="c1673-118">例如，可以使用长度为 5 的字符串“Hello”创建 [StringBuilder](xref:System.Text.StringBuilder) 类的新实例，同时可以指定该对象的最大容量为 25。</span><span class="sxs-lookup"><span data-stu-id="c1673-118">For example, you might create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="c1673-119">修改 [StringBuilder](xref:System.Text.StringBuilder) 时，在达到容量之前，该对象不会为自己重新分配空间。</span><span class="sxs-lookup"><span data-stu-id="c1673-119">When you modify the [StringBuilder](xref:System.Text.StringBuilder), it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="c1673-120">当达到容量时，将自动分配新的空间且容量翻倍。</span><span class="sxs-lookup"><span data-stu-id="c1673-120">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="c1673-121">可以使用重载的构造函数之一来指定 [StringBuilder](xref:System.Text.StringBuilder) 类的容量。</span><span class="sxs-lookup"><span data-stu-id="c1673-121">You can specify the capacity of the [StringBuilder](xref:System.Text.StringBuilder) class using one of the overloaded constructors.</span></span> <span data-ttu-id="c1673-122">下面的示例指定可以将 `MyStringBuilder` 对象增加到最多 25 个空间。</span><span class="sxs-lookup"><span data-stu-id="c1673-122">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

<span data-ttu-id="c1673-123">另外，可以使用读/写 [Capacity](xref:System.Text.StringBuilder.Capacity) 属性来设置对象的最大长度。</span><span class="sxs-lookup"><span data-stu-id="c1673-123">Additionally, you can use the read/write [Capacity](xref:System.Text.StringBuilder.Capacity) property to set the maximum length of your object.</span></span> <span data-ttu-id="c1673-124">下面的示例使用 [Capacity](xref:System.Text.StringBuilder.Capacity) 属性来定义对象的最大长度。</span><span class="sxs-lookup"><span data-stu-id="c1673-124">The following example uses the [Capacity](xref:System.Text.StringBuilder.Capacity) property to define the maximum object length.</span></span>

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

<span data-ttu-id="c1673-125">[EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) 方法可用来检查当前 [StringBuilder](xref:System.Text.StringBuilder) 的容量。</span><span class="sxs-lookup"><span data-stu-id="c1673-125">The [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) method can be used to check the capacity of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="c1673-126">如果容量大于传递的值，则不进行任何更改；但是，如果容量小于传递的值，则会更改当前的容量以使其与传递的值匹配。</span><span class="sxs-lookup"><span data-stu-id="c1673-126">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>

<span data-ttu-id="c1673-127">也可以查看或设置 [Length](xref:System.Text.StringBuilder.Length) 属性。</span><span class="sxs-lookup"><span data-stu-id="c1673-127">The [Length](xref:System.Text.StringBuilder.Length) property can also be viewed or set.</span></span> <span data-ttu-id="c1673-128">如果将 [Length](xref:System.Text.StringBuilder.Length) 属性设置为大于 [Capacity](xref:System.Text.StringBuilder.Capacity) 属性的值，则自动将 [Capacity](xref:System.Text.StringBuilder.Capacity) 属性更改为与 [Length](xref:System.Text.StringBuilder.Length) 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="c1673-128">If you set the [Length](xref:System.Text.StringBuilder.Length) property to a value that is greater than the [Capacity](xref:System.Text.StringBuilder.Capacity) property, the [Capacity](xref:System.Text.StringBuilder.Capacity) property is automatically changed to the same value as the [Length](xref:System.Text.StringBuilder.Length) property.</span></span> <span data-ttu-id="c1673-129">如果将 [Length](xref:System.Text.StringBuilder.Length) 属性设置为小于当前 [StringBuilder](xref:System.Text.StringBuilder) 对象内的字符串长度的值，则会缩短该字符串。</span><span class="sxs-lookup"><span data-stu-id="c1673-129">Setting the [Length](xref:System.Text.StringBuilder.Length) property to a value that is less than the length of the string within the current [StringBuilder](xref:System.Text.StringBuilder) shortens the string.</span></span>

## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="c1673-130">修改 StringBuilder 字符串</span><span class="sxs-lookup"><span data-stu-id="c1673-130">Modifying the StringBuilder String</span></span>

<span data-ttu-id="c1673-131">下表列出了可用于修改 [StringBuilder](xref:System.Text.StringBuilder) 内容的方法。</span><span class="sxs-lookup"><span data-stu-id="c1673-131">The following table lists the methods you can use to modify the contents of a [StringBuilder](xref:System.Text.StringBuilder).</span></span>

<span data-ttu-id="c1673-132">方法名称</span><span class="sxs-lookup"><span data-stu-id="c1673-132">Method name</span></span> | <span data-ttu-id="c1673-133">使用</span><span class="sxs-lookup"><span data-stu-id="c1673-133">Use</span></span>
----------- | ---
<span data-ttu-id="c1673-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span><span class="sxs-lookup"><span data-stu-id="c1673-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span></span> | <span data-ttu-id="c1673-135">将信息追加到当前 [StringBuilder](xref:System.Text.StringBuilder) 的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1673-135">Appends information to the end of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="c1673-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="c1673-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | <span data-ttu-id="c1673-137">用带格式文本替换字符串中传递的格式说明符。</span><span class="sxs-lookup"><span data-stu-id="c1673-137">Replaces a format specifier passed in a string with formatted text.</span></span>
<span data-ttu-id="c1673-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span><span class="sxs-lookup"><span data-stu-id="c1673-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span></span> | <span data-ttu-id="c1673-139">将字符串或对象插入到当前 [StringBuilder](xref:System.Text.StringBuilder) 的指定索引中。</span><span class="sxs-lookup"><span data-stu-id="c1673-139">Inserts a string or object into the specified index of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="c1673-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="c1673-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span></span> | <span data-ttu-id="c1673-141">从当前 [StringBuilder](xref:System.Text.StringBuilder) 中删除指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="c1673-141">Removes a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="c1673-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span><span class="sxs-lookup"><span data-stu-id="c1673-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span></span> | <span data-ttu-id="c1673-143">替换指定索引处的指定字符。</span><span class="sxs-lookup"><span data-stu-id="c1673-143">Replaces a specified character at a specified index.</span></span>

### <a name="append"></a><span data-ttu-id="c1673-144">追加</span><span class="sxs-lookup"><span data-stu-id="c1673-144">Append</span></span>

<span data-ttu-id="c1673-145">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) 方法可用来将文本或对象的字符串表示形式添加到由当前 [StringBuilder](xref:System.Text.StringBuilder) 表示的字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1673-145">The [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) method can be used to add text or a string representation of an object to the end of a string represented by the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="c1673-146">下面的示例将 [StringBuilder](xref:System.Text.StringBuilder) 对象初始化为“Hello World”，然后将一些文本追加到该对象的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1673-146">The following example initializes a [StringBuilder](xref:System.Text.StringBuilder) to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="c1673-147">将根据需要自动分配空间。</span><span class="sxs-lookup"><span data-stu-id="c1673-147">Space is allocated automatically as needed.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a><span data-ttu-id="c1673-148">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="c1673-148">AppendFormat</span></span>

<span data-ttu-id="c1673-149">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) 方法将文本添加到 [StringBuilder](xref:System.Text.StringBuilder) 对象的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1673-149">The [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) method adds text to the end of the [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="c1673-150">该方法通过调用要设置格式的对象的 [IFormattable](xref:System.IFormattable) 实现来支持复合格式设置功能（有关详细信息，请参阅[复合格式设置](composite-format.md)）。</span><span class="sxs-lookup"><span data-stu-id="c1673-150">It supports the composite formatting feature (for more information, see [Composite Formatting](composite-format.md)) by calling the [IFormattable](xref:System.IFormattable) implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="c1673-151">因此，它接受数字、日期和时间以及枚举值的标准格式字符串、数字以及日期和时间值的自定义格式字符串，以及为自定义类型定义的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="c1673-151">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="c1673-152">（有关格式化的信息，请参阅[格式设置类型](formatting-types.md)。）可以使用此方法来自定义变量的格式并将这些值追加到 [StringBuilder](xref:System.Text.StringBuilder)。</span><span class="sxs-lookup"><span data-stu-id="c1673-152">(For information about formatting, see [Formatting Types](formatting-types.md).) You can use this method to customize the format of variables and append those values to a [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="c1673-153">下面的示例使用 AppendFormat 方法将设置为货币值格式的整数值放到 [StringBuilder](xref:System.Text.StringBuilder) 对象的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1673-153">The following example uses the AppendFormat method to place an integer value formatted as a currency value at the end of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a><span data-ttu-id="c1673-154">Insert</span><span class="sxs-lookup"><span data-stu-id="c1673-154">Insert</span></span>

<span data-ttu-id="c1673-155">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) 方法将字符串或对象添加到当前 [StringBuilder](xref:System.Text.StringBuilder) 对象中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="c1673-155">The [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) method adds a string or object to a specified position in the current [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="c1673-156">下面的示例使用此方法将单词插入到 [StringBuilder](xref:System.Text.StringBuilder) 对象的第六个位置。</span><span class="sxs-lookup"><span data-stu-id="c1673-156">The following example uses this method to insert a word into the sixth position of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a><span data-ttu-id="c1673-157">删除</span><span class="sxs-lookup"><span data-stu-id="c1673-157">Remove</span></span>

<span data-ttu-id="c1673-158">可以使用 [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) 方法从当前 [StringBuilder](xref:System.Text.StringBuilder) 对象中删除指定数量的字符，删除过程从指定的从零开始的索引处开始。</span><span class="sxs-lookup"><span data-stu-id="c1673-158">You can use the [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to remove a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder) object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="c1673-159">下面的示例使用 [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) 方法缩短 [StringBuilder](xref:System.Text.StringBuilder) 对象。</span><span class="sxs-lookup"><span data-stu-id="c1673-159">The following example uses the [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to shorten a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a><span data-ttu-id="c1673-160">替换</span><span class="sxs-lookup"><span data-stu-id="c1673-160">Replace</span></span>

<span data-ttu-id="c1673-161">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | 替换指定索引处的指定字符。</span><span class="sxs-lookup"><span data-stu-id="c1673-161">The [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="c1673-162">方法可用于将 [StringBuilder](xref:System.Text.StringBuilder) 对象内的字符替换为其他指定字符。</span><span class="sxs-lookup"><span data-stu-id="c1673-162">method can be used to replace characters within the [StringBuilder](xref:System.Text.StringBuilder) object with another specified character.</span></span> <span data-ttu-id="c1673-163">以下示例使用 [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | 替换指定索引处的指定字符。</span><span class="sxs-lookup"><span data-stu-id="c1673-163">The following example uses the [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="c1673-164">方法在 [StringBuilder](xref:System.Text.StringBuilder) 对象中搜索感叹号字符 (!) 的所有实例，并将其替换为问号字符 (?)。</span><span class="sxs-lookup"><span data-stu-id="c1673-164">method to search a [StringBuilder](xref:System.Text.StringBuilder) object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="c1673-165">将 StringBuilder 对象转换为字符串</span><span class="sxs-lookup"><span data-stu-id="c1673-165">Converting a StringBuilder Object to a String</span></span>

<span data-ttu-id="c1673-166">必须先将 [StringBuilder](xref:System.Text.StringBuilder) 对象转换为 [String](xref:System.String) 对象，然后才能将 [StringBuilder](xref:System.Text.StringBuilder) 对象表示的字符串传递给具有 [String](xref:System.String) 参数的方法，或在用户界面中显示它。</span><span class="sxs-lookup"><span data-stu-id="c1673-166">You must convert the [StringBuilder](xref:System.Text.StringBuilder) object to a [String](xref:System.String) object before you can pass the string represented by the [StringBuilder](xref:System.Text.StringBuilder) object to a method that has a [String](xref:System.String) parameter or display it in the user interface.</span></span> <span data-ttu-id="c1673-167">通过调用 [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) 方法来执行此转换。</span><span class="sxs-lookup"><span data-stu-id="c1673-167">You do this conversion by calling the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method.</span></span> <span data-ttu-id="c1673-168">下面的示例调用多种 [StringBuilder](xref:System.Text.StringBuilder) 方法，然后调用 [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) 方法来显示字符串。</span><span class="sxs-lookup"><span data-stu-id="c1673-168">The following example calls a number of [StringBuilder](xref:System.Text.StringBuilder) methods and then calls the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method to display the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a><span data-ttu-id="c1673-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1673-169">See Also</span></span>

[<span data-ttu-id="c1673-170">System.Text.StringBuilder</span><span class="sxs-lookup"><span data-stu-id="c1673-170">System.Text.StringBuilder</span></span>](xref:System.Text.StringBuilder)

[<span data-ttu-id="c1673-171">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="c1673-171">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="c1673-172">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="c1673-172">Formatting types</span></span>](formatting-types.md)

