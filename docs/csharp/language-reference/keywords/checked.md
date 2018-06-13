---
title: checked（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: b05af798217a4f312bcf134d531135713efa8c66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216602"
---
# <a name="checked-c-reference"></a><span data-ttu-id="32024-102">checked（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="32024-102">checked (C# Reference)</span></span>
<span data-ttu-id="32024-103">`checked` 关键字用于对整型类型算术运算和转换显式启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="32024-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="32024-104">默认情况下，如果表达式仅包含常量值，且产生的值在目标类型范围之外，则会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="32024-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="32024-105">如果表达式包含一个或多个非常量值，则编译器不检测溢出。</span><span class="sxs-lookup"><span data-stu-id="32024-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="32024-106">在下面的示例中，计算赋给 `i2` 的表达式不会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="32024-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 <span data-ttu-id="32024-107">默认情况下，在运行时也不检查这些非常量表达式是否溢出，这些表达式不引发溢出异常。</span><span class="sxs-lookup"><span data-stu-id="32024-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="32024-108">上面的示例显示 -2,147,483,639 作为两个正整数之和。</span><span class="sxs-lookup"><span data-stu-id="32024-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="32024-109">可以通过编译器选项、环境配置或使用 `checked` 关键字来启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="32024-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="32024-110">下面的示例演示如何使用 `checked` 表达式或 `checked` 块，在运行时检测由前面的求和计算导致的溢出。</span><span class="sxs-lookup"><span data-stu-id="32024-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="32024-111">两个示例都引发溢出异常。</span><span class="sxs-lookup"><span data-stu-id="32024-111">Both examples raise an overflow exception.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 <span data-ttu-id="32024-112">可以使用 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 关键字阻止溢出检查。</span><span class="sxs-lookup"><span data-stu-id="32024-112">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32024-113">示例</span><span class="sxs-lookup"><span data-stu-id="32024-113">Example</span></span>  
 <span data-ttu-id="32024-114">此示例演示如何使用 `checked` 启用运行时溢出检查。</span><span class="sxs-lookup"><span data-stu-id="32024-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="32024-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="32024-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32024-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="32024-116">See Also</span></span>  
 [<span data-ttu-id="32024-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="32024-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="32024-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="32024-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="32024-119">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="32024-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="32024-120">Checked and Unchecked</span><span class="sxs-lookup"><span data-stu-id="32024-120">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="32024-121">unchecked</span><span class="sxs-lookup"><span data-stu-id="32024-121">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)
