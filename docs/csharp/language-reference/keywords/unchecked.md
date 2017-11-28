---
title: "unchecked（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords: unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c05e7cb742d8e8f5a7804656a5ec13548d0498b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="6ce14-102">unchecked（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6ce14-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="6ce14-103">`unchecked` 关键字用于取消整型类型的算术运算和转换的溢出检查。</span><span class="sxs-lookup"><span data-stu-id="6ce14-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="6ce14-104">在未经检查的上下文中，如果表达式生成的值超出目标类型的范围，则不会标记溢出。</span><span class="sxs-lookup"><span data-stu-id="6ce14-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="6ce14-105">例如，由于以下示例中的计算在 `unchecked` 块或表达式中执行，因此将忽略计算结果对于整数而言过大的事实，并且向 `int1` 赋予值 -2,147,483,639。</span><span class="sxs-lookup"><span data-stu-id="6ce14-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 <span data-ttu-id="6ce14-106">如果删除 `unchecked` 环境，会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="6ce14-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="6ce14-107">由于表达式的所有项都是常量，因此可在编译时检测到溢出。</span><span class="sxs-lookup"><span data-stu-id="6ce14-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="6ce14-108">在编译时和运行时，默认不检查包含非常数项的表达式。</span><span class="sxs-lookup"><span data-stu-id="6ce14-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="6ce14-109">请参阅[启用检查](../../../csharp/language-reference/keywords/checked.md)，获取有关使用启用了检查的环境的信息。</span><span class="sxs-lookup"><span data-stu-id="6ce14-109">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="6ce14-110">由于检查溢出需要时间，因此在没有溢出风险的情况下使用取消检查的代码可能会提高性能。</span><span class="sxs-lookup"><span data-stu-id="6ce14-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="6ce14-111">但是，如果存在溢出的可能，则应使用启用了检查的环境。</span><span class="sxs-lookup"><span data-stu-id="6ce14-111">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ce14-112">示例</span><span class="sxs-lookup"><span data-stu-id="6ce14-112">Example</span></span>  
 <span data-ttu-id="6ce14-113">此示例演示如何使用 `unchecked`关键字。</span><span class="sxs-lookup"><span data-stu-id="6ce14-113">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ce14-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6ce14-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ce14-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ce14-115">See Also</span></span>  
 [<span data-ttu-id="6ce14-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="6ce14-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6ce14-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="6ce14-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6ce14-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="6ce14-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6ce14-119">Checked and Unchecked</span><span class="sxs-lookup"><span data-stu-id="6ce14-119">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="6ce14-120">checked</span><span class="sxs-lookup"><span data-stu-id="6ce14-120">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)
