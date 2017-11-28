---
title: "Checked 和 Unchecked（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="a561b-102">Checked 和 Unchecked（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a561b-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="a561b-103">C# 语句既可以在已检查的上下文中执行，也可以在未检查的上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="a561b-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="a561b-104">在已检查的上下文中，算法溢出引发异常。</span><span class="sxs-lookup"><span data-stu-id="a561b-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="a561b-105">在未检查的上下文中，算法溢出被忽略并且结果被截断。</span><span class="sxs-lookup"><span data-stu-id="a561b-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="a561b-106">[checked](../../../csharp/language-reference/keywords/checked.md) 指定已检查的上下文。</span><span class="sxs-lookup"><span data-stu-id="a561b-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="a561b-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) 指定未检查的上下文。</span><span class="sxs-lookup"><span data-stu-id="a561b-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="a561b-108">如果既未指定 `unchecked``checked` 也未指定 ，则默认上下文取决于外部因素（如编译器选项）。</span><span class="sxs-lookup"><span data-stu-id="a561b-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="a561b-109">下列操作受溢出检查的影响：</span><span class="sxs-lookup"><span data-stu-id="a561b-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="a561b-110">表达式在整型上使用下列预定义运算符：</span><span class="sxs-lookup"><span data-stu-id="a561b-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="a561b-111">`++` `--` - (unary)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="a561b-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="a561b-112">整型间的显式数字转换。</span><span class="sxs-lookup"><span data-stu-id="a561b-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="a561b-113">使用 [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) 编译器选项，可以为非明确位于 `checked` 或 `unchecked` 关键字范围内的所有整型算术语句指定已检查或未检查的上下文。</span><span class="sxs-lookup"><span data-stu-id="a561b-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a561b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a561b-114">See Also</span></span>  
 [<span data-ttu-id="a561b-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a561b-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a561b-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a561b-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a561b-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a561b-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a561b-118">语句关键字</span><span class="sxs-lookup"><span data-stu-id="a561b-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
