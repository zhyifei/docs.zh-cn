---
title: "如何：串联多个字符串（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="e4245-102">如何：串联多个字符串（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e4245-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="e4245-103">串联是将一个字符串追加到另一字符串末尾的过程。</span><span class="sxs-lookup"><span data-stu-id="e4245-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="e4245-104">使用 `+` 运算符串联字符串文本或字符串常数时，编译器创建一个字符串。</span><span class="sxs-lookup"><span data-stu-id="e4245-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="e4245-105">不发生任何运行时串联。</span><span class="sxs-lookup"><span data-stu-id="e4245-105">No run time concatenation occurs.</span></span> <span data-ttu-id="e4245-106">但是，字符串变量仅可在运行时串联。</span><span class="sxs-lookup"><span data-stu-id="e4245-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="e4245-107">在这种情况下，你应当了解各种方法的性能影响。</span><span class="sxs-lookup"><span data-stu-id="e4245-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4245-108">示例</span><span class="sxs-lookup"><span data-stu-id="e4245-108">Example</span></span>  
 <span data-ttu-id="e4245-109">如下示例演示如何将长字符串文本拆分为较短的字符串，从而提高源代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="e4245-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="e4245-110">编译时将这些部分串联到一个字符串中。</span><span class="sxs-lookup"><span data-stu-id="e4245-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="e4245-111">无论涉及的字符串数量多少，均不存在运行时性能开销。</span><span class="sxs-lookup"><span data-stu-id="e4245-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 <span data-ttu-id="e4245-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e4245-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4245-113">示例</span><span class="sxs-lookup"><span data-stu-id="e4245-113">Example</span></span>  
 <span data-ttu-id="e4245-114">要串联字符串变量，可使用 `+` 或 `+=` 运算符，或者使用 <xref:System.String.Concat%2A?displayProperty=fullName>、<xref:System.String.Format%2A?displayProperty=fullName> 或 <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="e4245-114">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> methods.</span></span> <span data-ttu-id="e4245-115">`+` 运算符易于使用，有利于产生直观代码。</span><span class="sxs-lookup"><span data-stu-id="e4245-115">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="e4245-116">即使在一个语句中使用多个 + 运算符，字符串内容也仅会被复制一次。</span><span class="sxs-lookup"><span data-stu-id="e4245-116">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="e4245-117">但如果多次重复此操作，例如在循环中重复此操作，效率可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="e4245-117">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="e4245-118">例如，注意下面的代码：</span><span class="sxs-lookup"><span data-stu-id="e4245-118">For example, note the following code:</span></span>  
  
 <span data-ttu-id="e4245-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e4245-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4245-120">在字符串串联操作中，C# 编译器将 null 字符串和空字符串视为相同，但不转换原始 null 字符串的值。</span><span class="sxs-lookup"><span data-stu-id="e4245-120">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="e4245-121">如果不串联大量字符串（例如，在循环中），此代码的性能开销可能并不显著。</span><span class="sxs-lookup"><span data-stu-id="e4245-121">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="e4245-122">这一点同样适用于 <xref:System.String.Concat%2A?displayProperty=fullName> 和 <xref:System.String.Format%2A?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="e4245-122">The same is true for the <xref:System.String.Concat%2A?displayProperty=fullName> and <xref:System.String.Format%2A?displayProperty=fullName> methods.</span></span>  
  
 <span data-ttu-id="e4245-123">但是，如果性能极为重要，则应始终使用 <xref:System.Text.StringBuilder> 类来串联字符串。</span><span class="sxs-lookup"><span data-stu-id="e4245-123">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="e4245-124">如下代码使用 <xref:System.Text.StringBuilder> 类的 <xref:System.Text.StringBuilder.Append%2A> 方法串联字符串，不会产生 `+` 运算符的链式效应。</span><span class="sxs-lookup"><span data-stu-id="e4245-124">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 <span data-ttu-id="e4245-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e4245-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4245-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4245-126">See Also</span></span>  
 <span data-ttu-id="e4245-127"><xref:System.String></span><span class="sxs-lookup"><span data-stu-id="e4245-127"><xref:System.String></span></span>   
 <span data-ttu-id="e4245-128"><xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="e4245-128"><xref:System.Text.StringBuilder></span></span>   
 <span data-ttu-id="e4245-129">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4245-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e4245-130">字符串</span><span class="sxs-lookup"><span data-stu-id="e4245-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

