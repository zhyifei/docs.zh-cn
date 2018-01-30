---
title: "如何：串联多个字符串（C# 指南）"
description: "可以在 C# 中通过多种方法串联字符串。 了解多种选项和进行不同选择的原因。"
ms.date: 01/11/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4bc5e04edba48065746b96841b628ec5843c5e9
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="67bf4-104">如何：串联多个字符串（C# 指南）</span><span class="sxs-lookup"><span data-stu-id="67bf4-104">How to: Concatenate Multiple Strings (C# Guide)</span></span>

<span data-ttu-id="67bf4-105">串联是将一个字符串追加到另一字符串末尾的过程。</span><span class="sxs-lookup"><span data-stu-id="67bf4-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="67bf4-106">可通过使用 + 运算符串联字符串。</span><span class="sxs-lookup"><span data-stu-id="67bf4-106">You concatenate strings by using the + operator.</span></span> <span data-ttu-id="67bf4-107">对于字符串文本和字符串常量，会在编译时进行串联，运行时不串联。</span><span class="sxs-lookup"><span data-stu-id="67bf4-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="67bf4-108">对于字符串变量，仅在运行时窗帘。</span><span class="sxs-lookup"><span data-stu-id="67bf4-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="67bf4-109">以下示例通过串联将长字符串文本拆分为较短的字符串，从而提高源代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="67bf4-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="67bf4-110">编译时将这些部分串联到一个字符串中。</span><span class="sxs-lookup"><span data-stu-id="67bf4-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="67bf4-111">无论涉及到多少个字符串，均不产生运行时性能开销。</span><span class="sxs-lookup"><span data-stu-id="67bf4-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  
  

<span data-ttu-id="67bf4-112">要串联字符串变量，可使用 `+` 或 `+=` 运算符、[字符串内插](../tutorials/string-interpolation.md)或 <xref:System.String.Concat%2A?displayProperty=nameWithType>、<xref:System.String.Format%2A?displayProperty=nameWithType>、<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="67bf4-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../tutorials/string-interpolation.md) or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="67bf4-113">`+` 运算符易于使用，有利于产生直观代码。</span><span class="sxs-lookup"><span data-stu-id="67bf4-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="67bf4-114">即使在一个语句中使用多个 + 运算符，字符串内容也仅会被复制一次。</span><span class="sxs-lookup"><span data-stu-id="67bf4-114">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="67bf4-115">以下代码演示两个使用 `+` 运算符串联字符串的示例：</span><span class="sxs-lookup"><span data-stu-id="67bf4-115">The following code shows two examples of using the `+` operator to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="67bf4-116">在某些表达式中，使用字符串内插进行字符串串联更简单，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="67bf4-116">In some expressions, it is easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
>  <span data-ttu-id="67bf4-117">在字符串串联操作中，C# 编译器将 null 字符串视为空字符串进行处理。</span><span class="sxs-lookup"><span data-stu-id="67bf4-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="67bf4-118">其他字符串串联方法包括 <xref:System.String.Concat%2A?displayProperty=nameWithType> 和 <xref:System.String.Format%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="67bf4-118">Other methods to concatenate strings are <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="67bf4-119">这些方法非常适用于从少量组件字符串生成字符串的情况。</span><span class="sxs-lookup"><span data-stu-id="67bf4-119">These methods work well when you are building a string from a small number of component strings.</span></span> <span data-ttu-id="67bf4-120">如果知道构成串连字符串的字符串数量，同样适合选择这些方法。</span><span class="sxs-lookup"><span data-stu-id="67bf4-120">These methdos are also a great choice when you know the number of strings that make up your concatenated string.</span></span>

<span data-ttu-id="67bf4-121">在其他情况下，可能要将字符串合并在循环中，此时不知道要合并的源字符串的数量，而且源字符串的实际数量可能非常大。</span><span class="sxs-lookup"><span data-stu-id="67bf4-121">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="67bf4-122"><xref:System.Text.StringBuilder> 类专门用于此类方案。</span><span class="sxs-lookup"><span data-stu-id="67bf4-122">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="67bf4-123">以下代码使用 <xref:System.Text.StringBuilder> 类的 <xref:System.Text.StringBuilder.Append%2A> 方法串联字符串。</span><span class="sxs-lookup"><span data-stu-id="67bf4-123">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="67bf4-124">有关详细信息，请阅读[选择字符串串联或 `StringBuilder` 类的原因](xref:System.Text.StringBuilder#StringAndSB)</span><span class="sxs-lookup"><span data-stu-id="67bf4-124">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB)</span></span>

<span data-ttu-id="67bf4-125">还可使用 [LINQ](../programming-guide/concepts/linq/index.md) 和 <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> 方法联接集合中的字符串。</span><span class="sxs-lookup"><span data-stu-id="67bf4-125">Another option to join strings from a collection is to use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="67bf4-126">此方法利用 lambda 表达式合并源字符串。</span><span class="sxs-lookup"><span data-stu-id="67bf4-126">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="67bf4-127">lambda 表达式用于将所有字符串添加到现有累积。</span><span class="sxs-lookup"><span data-stu-id="67bf4-127">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="67bf4-128">下面的示例通过在数组中的每两个单词之间添加一个空格来合并一组单词：</span><span class="sxs-lookup"><span data-stu-id="67bf4-128">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]  


## <a name="see-also"></a><span data-ttu-id="67bf4-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="67bf4-129">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="67bf4-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="67bf4-130">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="67bf4-131">字符串</span><span class="sxs-lookup"><span data-stu-id="67bf4-131">Strings</span></span>](../programming-guide/strings/index.md)
