---
title: "填充字符串"
description: "填充字符串"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bc3cc9028b232cc2ba6ca3130c4bdb261c4a0a42
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="padding-strings"></a><span data-ttu-id="55a01-104">填充字符串</span><span class="sxs-lookup"><span data-stu-id="55a01-104">Padding strings</span></span>

<span data-ttu-id="55a01-105">使用以下 [System.String](xref:System.String) 方法之一可创建由使用前导或尾随字符填充到指定总长度的原始字符串组成的新字符串。</span><span class="sxs-lookup"><span data-stu-id="55a01-105">Use one of the following [System.String](xref:System.String) methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="55a01-106">填充字符可以是空格或指定字符，因而显示为右对齐或左对齐。</span><span class="sxs-lookup"><span data-stu-id="55a01-106">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>

<span data-ttu-id="55a01-107">方法名称</span><span class="sxs-lookup"><span data-stu-id="55a01-107">Method name</span></span> | <span data-ttu-id="55a01-108">使用</span><span class="sxs-lookup"><span data-stu-id="55a01-108">Use</span></span>
----------- | ---
<span data-ttu-id="55a01-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="55a01-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span></span> | <span data-ttu-id="55a01-110">使用前导字符将字符串填充到指定总长度。</span><span class="sxs-lookup"><span data-stu-id="55a01-110">Pads a string with leading characters to a specified total length.</span></span>
<span data-ttu-id="55a01-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="55a01-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span></span> | <span data-ttu-id="55a01-112">使用尾随字符将字符串填充到指定总长度。</span><span class="sxs-lookup"><span data-stu-id="55a01-112">Pads a string with trailing characters to a specified total length.</span></span>

## <a name="padleft"></a><span data-ttu-id="55a01-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="55a01-113">PadLeft</span></span>

<span data-ttu-id="55a01-114">[String.PadLeft](xref:System.String.PadLeft(System.Int32)) 方法将足够前导填充字符连接到原始字符串来达到指定总长度，从而创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="55a01-114">The [String.PadLeft](xref:System.String.PadLeft(System.Int32)) method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="55a01-115">[String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) 方法使用空格作为填充字符，[String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) 方法使你可以指定自己的填充字符。</span><span class="sxs-lookup"><span data-stu-id="55a01-115">The [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) method uses white space as the padding character and the [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="55a01-116">下面的代码示例使用 [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) 方法创建一个长度为&20; 个字符的新字符串。</span><span class="sxs-lookup"><span data-stu-id="55a01-116">The following code example uses the [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="55a01-117">该示例向控制台显示“`--------Hello World!`”。</span><span class="sxs-lookup"><span data-stu-id="55a01-117">The example displays "`--------Hello World!`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a><span data-ttu-id="55a01-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="55a01-118">PadRight</span></span>

<span data-ttu-id="55a01-119">[String.PadRight](xref:System.String.PadRight(System.Int32)) 方法将足够尾随填充字符连接到原始字符串来达到指定总长度，从而创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="55a01-119">The [String.PadRight](xref:System.String.PadRight(System.Int32)) method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="55a01-120">[String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) 方法使用空格作为填充字符，[String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) 方法使你可以指定自己的填充字符。</span><span class="sxs-lookup"><span data-stu-id="55a01-120">The [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) method uses white space as the padding character and the [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="55a01-121">下面的代码示例使用 [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) 方法创建一个长度为&20; 个字符的新字符串。</span><span class="sxs-lookup"><span data-stu-id="55a01-121">The following code example uses the [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="55a01-122">该示例向控制台显示“`Hello World!--------`”。</span><span class="sxs-lookup"><span data-stu-id="55a01-122">The example displays "`Hello World!--------`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a><span data-ttu-id="55a01-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55a01-123">See Also</span></span>

[<span data-ttu-id="55a01-124">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="55a01-124">Basic string operations</span></span>](basic-string-operations.md)


