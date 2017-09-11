---
title: "从字符串剪裁和移除字符"
description: "从字符串剪裁和移除字符"
keywords: ".NET、.NET Core"
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
ms.translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 96cf08c0de8ba73d931d561187369ccf8b091651
ms.contentlocale: zh-cn
ms.lasthandoff: 11/05/2016

---

# <a name="trimming-and-removing-characters-from-strings"></a><span data-ttu-id="51d47-104">从字符串剪裁和移除字符</span><span class="sxs-lookup"><span data-stu-id="51d47-104">Trimming and removing characters from strings</span></span>

<span data-ttu-id="51d47-105">如果将句子分析成单个单词，最后得到的结果可能是任意一端带有空白（也称为空格）的单词。</span><span class="sxs-lookup"><span data-stu-id="51d47-105">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="51d47-106">在这种情形下，可以使用 [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) 类中的其中一种剪裁方法，从字符串中的指定位置移除任何数量的空格或其他字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-106">In this situation, you can use one of the trim methods in the [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="51d47-107">下表描述了可用的剪裁方法。</span><span class="sxs-lookup"><span data-stu-id="51d47-107">The following table describes the available trim methods.</span></span>

<span data-ttu-id="51d47-108">方法名称</span><span class="sxs-lookup"><span data-stu-id="51d47-108">Method name</span></span> | <span data-ttu-id="51d47-109">使用</span><span class="sxs-lookup"><span data-stu-id="51d47-109">Use</span></span>
----------- | ---
[<span data-ttu-id="51d47-110">String.Trim</span><span class="sxs-lookup"><span data-stu-id="51d47-110">String.Trim</span></span>](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | <span data-ttu-id="51d47-111">从字符串的开头和结尾移除空白或者指定的字符</span><span class="sxs-lookup"><span data-stu-id="51d47-111">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>
<span data-ttu-id="51d47-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="51d47-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span></span> | <span data-ttu-id="51d47-113">从字符串的结尾移除在字符数组中指定的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-113">Removes characters specified in an array of characters from the end of a string.</span></span>
<span data-ttu-id="51d47-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="51d47-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span></span> | <span data-ttu-id="51d47-115">从字符串的开头移除在字符数组中指定的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-115">Removes characters specified in an array of characters from the beginning of a string.</span></span>
<span data-ttu-id="51d47-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="51d47-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span></span> | <span data-ttu-id="51d47-117">从字符串中的指定索引位置移除指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-117">Removes a specified number of characters from a specified index position in a string.</span></span>


## <a name="trim"></a><span data-ttu-id="51d47-118">Trim</span><span class="sxs-lookup"><span data-stu-id="51d47-118">Trim</span></span>

<span data-ttu-id="51d47-119">通过使用 [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) 方法，可以方便地从字符串两端移除空白，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="51d47-119">You can easily remove white spaces from both ends of a string by using the [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) method, as shown in the following example.</span></span>

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

<span data-ttu-id="51d47-120">还可以从字符串的开始和结尾移除指定的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-120">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="51d47-121">下面的示例将移除空白字符、句点和星号。</span><span class="sxs-lookup"><span data-stu-id="51d47-121">The following example removes white-space characters, periods, and asterisks.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a><span data-ttu-id="51d47-122">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="51d47-122">TrimEnd</span></span>

<span data-ttu-id="51d47-123">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 方法从字符串的结尾移除字符，同时创建新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="51d47-123">The [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="51d47-124">通过向此方法传递一个字符数组来指定要移除的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-124">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="51d47-125">字符数组中的元素顺序并不影响剪裁操作。</span><span class="sxs-lookup"><span data-stu-id="51d47-125">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="51d47-126">找到未在数组中指定的字符时，剪裁停止。</span><span class="sxs-lookup"><span data-stu-id="51d47-126">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="51d47-127">下面的示例使用 TrimEnd 方法移除字符串最后面的字母。</span><span class="sxs-lookup"><span data-stu-id="51d47-127">The following example removes the last letters of a string using the TrimEnd method.</span></span> <span data-ttu-id="51d47-128">在此示例中，`'r'` 字符和 `'W'` 字符的位置交换，说明数组中字符的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="51d47-128">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="51d47-129">请注意，此代码移除 `MyString` 的最后一个单词和第一个单词的一部分。</span><span class="sxs-lookup"><span data-stu-id="51d47-129">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="51d47-130">此代码向控制台显示 `He`。</span><span class="sxs-lookup"><span data-stu-id="51d47-130">This code displays `He` to the console.</span></span>

<span data-ttu-id="51d47-131">下面的示例使用 [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 方法移除字符串的最后一个单词。</span><span class="sxs-lookup"><span data-stu-id="51d47-131">The following example removes the last word of a string using the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method.</span></span> <span data-ttu-id="51d47-132">在此代码中，单词 `Hello` 后跟一个逗号，而由于在要剪裁的字符数组中未指定逗号，因此剪裁在逗号处结束。</span><span class="sxs-lookup"><span data-stu-id="51d47-132">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="51d47-133">此代码向控制台显示 `Hello,`。</span><span class="sxs-lookup"><span data-stu-id="51d47-133">This code displays `Hello,` to the console.</span></span>

## <a name="trimstart"></a><span data-ttu-id="51d47-134">TrimStart</span><span class="sxs-lookup"><span data-stu-id="51d47-134">TrimStart</span></span>

<span data-ttu-id="51d47-135">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) 方法类似于 [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 方法，不同之处在于它通过从现有字符串对象的开头移除字符来创建新的字符串。</span><span class="sxs-lookup"><span data-stu-id="51d47-135">The [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method is similar to the [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="51d47-136">通过向 [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) 方法传递一个字符数组来指定要移除的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-136">An array of characters is passed to the [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method to specify the characters to be removed.</span></span> <span data-ttu-id="51d47-137">与 [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 方法一样，字符数组中元素的顺序并不影响剪裁操作。</span><span class="sxs-lookup"><span data-stu-id="51d47-137">As with the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="51d47-138">找到未在数组中指定的字符时，剪裁停止。</span><span class="sxs-lookup"><span data-stu-id="51d47-138">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="51d47-139">下面的示例移除字符串的第一个单词。</span><span class="sxs-lookup"><span data-stu-id="51d47-139">The following example removes the first word of a string.</span></span> <span data-ttu-id="51d47-140">在此示例中，`'l'` 字符和 `'H'` 字符的位置交换，说明数组中字符的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="51d47-140">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="51d47-141">此代码向控制台显示 `World!`。</span><span class="sxs-lookup"><span data-stu-id="51d47-141">This code displays `World!` to the console.</span></span>

## <a name="remove"></a><span data-ttu-id="51d47-142">删除</span><span class="sxs-lookup"><span data-stu-id="51d47-142">Remove</span></span>

<span data-ttu-id="51d47-143">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) 方法从现有字符串的指定位置开始移除指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-143">The [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="51d47-144">此方法采用从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="51d47-144">This method assumes a zero-based index.</span></span>

<span data-ttu-id="51d47-145">下面的示例在字符串从零开始的索引中第五个位置开始移除十个字符。</span><span class="sxs-lookup"><span data-stu-id="51d47-145">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

<span data-ttu-id="51d47-146">通过调用 [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) 方法并指定空字符串 ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) 作为替代，也可以从字符串中移除指定字符或子字符串。</span><span class="sxs-lookup"><span data-stu-id="51d47-146">You can also remove a specified character or substring from a string by calling the [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) method and specifying an empty string ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) as the replacement.</span></span> <span data-ttu-id="51d47-147">下面的示例从字符串中移除所有逗号。</span><span class="sxs-lookup"><span data-stu-id="51d47-147">The following example removes all commas from a string.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a><span data-ttu-id="51d47-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51d47-148">See Also</span></span>

[<span data-ttu-id="51d47-149">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="51d47-149">Basic string operations</span></span>](basic-string-operations.md)


