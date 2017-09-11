---
title: "更改大小写"
description: "更改大小写"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a><span data-ttu-id="7afb8-104">更改大小写</span><span class="sxs-lookup"><span data-stu-id="7afb8-104">Changing case</span></span>

<span data-ttu-id="7afb8-105">如果编写可接受用户输入的应用程序，永远无法确定用户以哪种大小写输入数据。</span><span class="sxs-lookup"><span data-stu-id="7afb8-105">If you write an application that accepts input from a user, you can never be sure what case he or she will use to enter the data.</span></span> <span data-ttu-id="7afb8-106">通常，你希望字符串统一采用大写或小写，尤其是在用户界面显示时。</span><span class="sxs-lookup"><span data-stu-id="7afb8-106">Often, you want strings to be cased consistently, particularly if you are displaying them in the user interface.</span></span> <span data-ttu-id="7afb8-107">下表描述两个大小写更改方法。</span><span class="sxs-lookup"><span data-stu-id="7afb8-107">The following table describes two case-changing methods.</span></span>

<span data-ttu-id="7afb8-108">方法名称</span><span class="sxs-lookup"><span data-stu-id="7afb8-108">Method name</span></span> | <span data-ttu-id="7afb8-109">使用</span><span class="sxs-lookup"><span data-stu-id="7afb8-109">Use</span></span>
----------- | ---
[<span data-ttu-id="7afb8-110">String.ToUpper</span><span class="sxs-lookup"><span data-stu-id="7afb8-110">String.ToUpper</span></span>](xref:System.String.ToUpper) | <span data-ttu-id="7afb8-111">将字符串中的所有字符均转换为大写。</span><span class="sxs-lookup"><span data-stu-id="7afb8-111">Converts all characters in a string to uppercase.</span></span>
[<span data-ttu-id="7afb8-112">String.ToLower</span><span class="sxs-lookup"><span data-stu-id="7afb8-112">String.ToLower</span></span>](xref:System.String.ToLower) | <span data-ttu-id="7afb8-113">将字符串中的所有字符均转换为小写。</span><span class="sxs-lookup"><span data-stu-id="7afb8-113">Converts all characters in a string to lowercase.</span></span>

> [!WARNING]  
> <span data-ttu-id="7afb8-114">请注意，为了对 `String.ToUpper` 和 `String.ToLower` 方法进行比较或测试它们是否相等，这两种方法不应用于转换字符串。</span><span class="sxs-lookup"><span data-stu-id="7afb8-114">Note that the `String.ToUpper` and `String.ToLower` methods should not be used to convert strings in order to compare them or test them for equality.</span></span> 

## <a name="comparing-strings-of-mixed-case"></a><span data-ttu-id="7afb8-115">比较混合大小写的字符串</span><span class="sxs-lookup"><span data-stu-id="7afb8-115">Comparing strings of mixed case</span></span>

<span data-ttu-id="7afb8-116">若要比较混合大小写的字符串以确定它们是否相等，请调用具有 [String](xref:System) `Equals` 方法中具有 *comparisonType* 参数的重载之一，并为 *comparisonType* 自变量提供 [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) 或 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 值。</span><span class="sxs-lookup"><span data-stu-id="7afb8-116">To compare strings of mixed case to determine whether they are equal, their, call one of the overloads of the [String](xref:System) `Equals` method with a *comparisonType* parameter, and provide a value of either [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for the *comparisonType* argument.</span></span> 

<span data-ttu-id="7afb8-117">有关详细信息，请参阅[有关使用字符串的最佳实践](best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="7afb8-117">For more information, see [Best Practices for Using Strings](best-practices.md).</span></span> 

## <a name="toupper"></a><span data-ttu-id="7afb8-118">ToUpper</span><span class="sxs-lookup"><span data-stu-id="7afb8-118">ToUpper</span></span>

<span data-ttu-id="7afb8-119">[String.ToUpper](xref:System.String.ToUpper) 方法将字符串中的所有字符更改为大写。</span><span class="sxs-lookup"><span data-stu-id="7afb8-119">The [String.ToUpper](xref:System.String.ToUpper) method changes all characters in a string to uppercase.</span></span> <span data-ttu-id="7afb8-120">下面的示例将字符串“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="7afb8-120">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="7afb8-121">从混合大小写转换为大写。</span><span class="sxs-lookup"><span data-stu-id="7afb8-121">from mixed case to uppercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a><span data-ttu-id="7afb8-122">ToLower</span><span class="sxs-lookup"><span data-stu-id="7afb8-122">ToLower</span></span>

<span data-ttu-id="7afb8-123">[String.ToLower](xref:System.String.ToLower) 方法与上述方法类似，但改为将字符串中的所有字符均转换为小写。</span><span class="sxs-lookup"><span data-stu-id="7afb8-123">The [String.ToLower](xref:System.String.ToLower) method is similar to the previous method, but instead converts all the characters in a string to lowercase.</span></span> <span data-ttu-id="7afb8-124">下面的示例将字符串“Hello World!”转换为</span><span class="sxs-lookup"><span data-stu-id="7afb8-124">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="7afb8-125">小写。</span><span class="sxs-lookup"><span data-stu-id="7afb8-125">to lowercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a><span data-ttu-id="7afb8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7afb8-126">See Also</span></span>

[<span data-ttu-id="7afb8-127">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="7afb8-127">Basic string operations</span></span>](basic-string-operations.md)

