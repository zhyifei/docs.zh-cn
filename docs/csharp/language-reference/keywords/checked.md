---
title: "checked（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-reference"></a><span data-ttu-id="6bba8-102">checked（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6bba8-102">checked (C# Reference)</span></span>
<span data-ttu-id="6bba8-103">`checked` 关键字用于对整型类型算术运算和转换显式启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="6bba8-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="6bba8-104">默认情况下，如果表达式仅包含常量值，且产生的值在目标类型范围之外，则会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="6bba8-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="6bba8-105">如果表达式包含一个或多个非常量值，则编译器不检测溢出。</span><span class="sxs-lookup"><span data-stu-id="6bba8-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="6bba8-106">在下面的示例中，计算赋给 `i2` 的表达式不会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="6bba8-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 <span data-ttu-id="6bba8-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6bba8-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span></span>  
  
 <span data-ttu-id="6bba8-108">默认情况下，在运行时也不检查这些非常量表达式是否溢出，这些表达式不引发溢出异常。</span><span class="sxs-lookup"><span data-stu-id="6bba8-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="6bba8-109">上面的示例显示 -2,147,483,639 作为两个正整数之和。</span><span class="sxs-lookup"><span data-stu-id="6bba8-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="6bba8-110">可以通过编译器选项、环境配置或使用 `checked` 关键字来启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="6bba8-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="6bba8-111">下面的示例演示如何使用 `checked` 表达式或 `checked` 块，在运行时检测由前面的求和计算导致的溢出。</span><span class="sxs-lookup"><span data-stu-id="6bba8-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="6bba8-112">两个示例都引发溢出异常。</span><span class="sxs-lookup"><span data-stu-id="6bba8-112">Both examples raise an overflow exception.</span></span>  
  
 <span data-ttu-id="6bba8-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6bba8-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span></span>  
  
 <span data-ttu-id="6bba8-114">可以使用 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 关键字阻止溢出检查。</span><span class="sxs-lookup"><span data-stu-id="6bba8-114">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bba8-115">示例</span><span class="sxs-lookup"><span data-stu-id="6bba8-115">Example</span></span>  
 <span data-ttu-id="6bba8-116">此示例演示如何使用 `checked` 启用运行时溢出检查。</span><span class="sxs-lookup"><span data-stu-id="6bba8-116">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 <span data-ttu-id="6bba8-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6bba8-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6bba8-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6bba8-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6bba8-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bba8-119">See Also</span></span>  
 <span data-ttu-id="6bba8-120">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bba8-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6bba8-121">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bba8-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6bba8-122">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bba8-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6bba8-123">[Checked 和 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="6bba8-123">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="6bba8-124">unchecked</span><span class="sxs-lookup"><span data-stu-id="6bba8-124">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)

