---
title: "创建新字符串"
description: "创建新字符串"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 793b5bc4b26967104459fa2559c6127bb82f3a9d
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="creating-new-strings"></a><span data-ttu-id="1d085-104">创建新字符串</span><span class="sxs-lookup"><span data-stu-id="1d085-104">Creating new strings</span></span>

<span data-ttu-id="1d085-105">.NET 允许通过简单赋值创建字符串，并且还重载一个类构造函数，以支持使用一些不同参数来创建字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-105">.NET  allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="1d085-106">.NET 还在 [System.String](xref:System.String) 类中提供了几个方法，这些方法通过合并多个字符串、字符串数组或对象来创建新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="1d085-106">.NET also provides several methods in the [System.String](xref:System.String) class that create new string objects by combining several strings, arrays of strings, or objects.</span></span> 

## <a name="creating-strings-using-assignment"></a><span data-ttu-id="1d085-107">通过赋值创建字符串</span><span class="sxs-lookup"><span data-stu-id="1d085-107">Creating Strings Using Assignment</span></span>

<span data-ttu-id="1d085-108">创建新 [String](xref:System.String) 对象的最简单方法是将一个字符串赋给 [String](xref:System.String) 对象。</span><span class="sxs-lookup"><span data-stu-id="1d085-108">The easiest way to create a new [String](xref:System.String) object is simply to assign a string literal to a [String](xref:System.String) object.</span></span> 

## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="1d085-109">使用类构造函数创建字符串</span><span class="sxs-lookup"><span data-stu-id="1d085-109">Creating Strings Using a Class Constructor</span></span>

<span data-ttu-id="1d085-110">可以使用 [String](xref:System.String) 类构造函数的重载从字符数组创建字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-110">You can use overloads of the [String](xref:System.String) class constructor to create strings from character arrays.</span></span> <span data-ttu-id="1d085-111">还可以通过将特定字符重复指定次数来创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-111">You can also create a new string by duplicating a particular character a specified number of times.</span></span> 

## <a name="methods-that-return-strings"></a><span data-ttu-id="1d085-112">返回字符串的方法</span><span class="sxs-lookup"><span data-stu-id="1d085-112">Methods that Return Strings</span></span>

<span data-ttu-id="1d085-113">下表列出了返回新字符串对象的几个有用方法。</span><span class="sxs-lookup"><span data-stu-id="1d085-113">The following table lists several useful methods that return new string objects.</span></span>

<span data-ttu-id="1d085-114">方法名称</span><span class="sxs-lookup"><span data-stu-id="1d085-114">Method name</span></span> | <span data-ttu-id="1d085-115">使用</span><span class="sxs-lookup"><span data-stu-id="1d085-115">Use</span></span>
----------- | ---
<span data-ttu-id="1d085-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="1d085-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span></span> | <span data-ttu-id="1d085-117">从一组输入对象生成格式化的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-117">Builds a formatted string from a set of input objects.</span></span>
<span data-ttu-id="1d085-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span><span class="sxs-lookup"><span data-stu-id="1d085-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span></span> | <span data-ttu-id="1d085-119">从两个或更多个字符串生成字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-119">Builds strings from two or more strings.</span></span>
<span data-ttu-id="1d085-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span><span class="sxs-lookup"><span data-stu-id="1d085-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span></span> |<span data-ttu-id="1d085-121">通过合并字符串数组生成新字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-121">Builds a new string by combining an array of strings.</span></span>
<span data-ttu-id="1d085-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span><span class="sxs-lookup"><span data-stu-id="1d085-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span></span> | <span data-ttu-id="1d085-123">通过将一个字符串插入现有字符串的指定索引处生成新字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-123">Builds a new string by inserting a string into the specified index of an existing string.</span></span>
<span data-ttu-id="1d085-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="1d085-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span></span> | <span data-ttu-id="1d085-125">将一个字符串中的指定字符复制到一个字符数组中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="1d085-125">Copies specified characters in a string into a specified position in an array of characters.</span></span>

### <a name="format"></a><span data-ttu-id="1d085-126">格式</span><span class="sxs-lookup"><span data-stu-id="1d085-126">Format</span></span>

<span data-ttu-id="1d085-127">可以使用 `String.Format` 方法创建格式化字符串和连接表示多个对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-127">You can use the `String.Format` method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="1d085-128">此方法自动将传递给它的任何对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-128">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="1d085-129">例如，如果应用程序必须向用户显示 [Int32](xref:System.Int32) 值和 [DateTime](xref:System.DateTime) 值，则可以很方便地使用 `Format` 方法来构造表示这些值的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-129">For example, if your application must display an [Int32](xref:System.Int32) value and a [DateTime](xref:System.DateTime) value to the user, you can easily construct a string to represent these values using the `Format` method.</span></span> <span data-ttu-id="1d085-130">有关此方法使用的格式化约定的信息，请参阅有关[复合格式化](composite-format.md)的部分。</span><span class="sxs-lookup"><span data-stu-id="1d085-130">For information about formatting conventions used with this method, see the section on [composite formatting](composite-format.md).</span></span>

<span data-ttu-id="1d085-131">下面的示例使用 `Format` 方法创建一个使用整数变量的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-131">The following example uses the `Format` method to create a string that uses an integer variable.</span></span>

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

<span data-ttu-id="1d085-132">在此示例中，[DateTime.Now](xref:System.DateTime.Now) 按照与当前线程关联的区域性所指定的方式来显示当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1d085-132">In this example, [DateTime.Now](xref:System.DateTime.Now) displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>

### <a name="concat"></a><span data-ttu-id="1d085-133">Concat</span><span class="sxs-lookup"><span data-stu-id="1d085-133">Concat</span></span>

<span data-ttu-id="1d085-134">`String.Concat` 方法可用来方便地从两个或更多个现有对象创建新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="1d085-134">The `String.Concat` method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="1d085-135">它提供了一种与语言无关的方法来连接字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-135">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="1d085-136">此方法接受派生自 `System.Object` 的任何类。</span><span class="sxs-lookup"><span data-stu-id="1d085-136">This method accepts any class that derives from `System.Object`.</span></span> <span data-ttu-id="1d085-137">下面的示例使用两个现有字符串对象和一个分隔符创建一个字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-137">The following example creates a string from two existing string objects and a separating character.</span></span>

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a><span data-ttu-id="1d085-138">联接</span><span class="sxs-lookup"><span data-stu-id="1d085-138">Join</span></span>

<span data-ttu-id="1d085-139">`String.Join` 方法通过一个字符串数组和一个分隔符串创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-139">The `String.Join` method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="1d085-140">如果想要将多个字符串连接在一起，构成一个可能由逗号分隔的列表，则此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="1d085-140">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>

<span data-ttu-id="1d085-141">下面的示例使用空格来连接字符串数组。</span><span class="sxs-lookup"><span data-stu-id="1d085-141">The following example uses a space to bind a string array.</span></span>

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a><span data-ttu-id="1d085-142">Insert</span><span class="sxs-lookup"><span data-stu-id="1d085-142">Insert</span></span>

<span data-ttu-id="1d085-143">`String.Insert` 方法通过将一个字符串插入另一个字符串中的指定位置来创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-143">The `String.Insert` method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="1d085-144">此方法使用从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="1d085-144">This method uses a zero-based index.</span></span> <span data-ttu-id="1d085-145">下面的示例将一个字符串插入 `MyString` 的第五个索引位置，并用此值创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="1d085-145">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a><span data-ttu-id="1d085-146">CopyTo</span><span class="sxs-lookup"><span data-stu-id="1d085-146">CopyTo</span></span>

<span data-ttu-id="1d085-147">`String.CopyTo` 方法将字符串的某些部分复制到字符数组中。</span><span class="sxs-lookup"><span data-stu-id="1d085-147">The `String.CopyTo` method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="1d085-148">可以同时指定字符串的开始索引和要复制的字符数。</span><span class="sxs-lookup"><span data-stu-id="1d085-148">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="1d085-149">此方法采用源索引、字符数组、目标索引和要复制的字符数。</span><span class="sxs-lookup"><span data-stu-id="1d085-149">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="1d085-150">所有索引都从零开始。</span><span class="sxs-lookup"><span data-stu-id="1d085-150">All indexes are zero-based.</span></span>

<span data-ttu-id="1d085-151">下面的示例使用 `CopyTo` 方法将单词“Hello”的字符从字符串对象复制到字符数组的第一个索引位置。</span><span class="sxs-lookup"><span data-stu-id="1d085-151">The following example uses the `CopyTo` method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a><span data-ttu-id="1d085-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d085-152">See Also</span></span>

[<span data-ttu-id="1d085-153">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="1d085-153">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="1d085-154">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="1d085-154">Composite formatting</span></span>](composite-format.md)


