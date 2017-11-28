---
title: "continue（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords: continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1ace2c90d03593b51b9ea461a47e122c5da1ab81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="continue-c-reference"></a><span data-ttu-id="f98e8-102">continue（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f98e8-102">continue (C# Reference)</span></span>
<span data-ttu-id="f98e8-103">`continue` 语句将控制传递到其中出现的封闭 [while](../../../csharp/language-reference/keywords/while.md)、[do](../../../csharp/language-reference/keywords/do.md)、[for](../../../csharp/language-reference/keywords/for.md) 或 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="f98e8-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f98e8-104">示例</span><span class="sxs-lookup"><span data-stu-id="f98e8-104">Example</span></span>  
 <span data-ttu-id="f98e8-105">在本示例中，计数器最初是从 1 到 10 进行计数。</span><span class="sxs-lookup"><span data-stu-id="f98e8-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="f98e8-106">通过结合使用 `continue` 语句和表达式 `(i < 9)`，跳过 `continue` 和 `for` 主体末尾之间的语句。</span><span class="sxs-lookup"><span data-stu-id="f98e8-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f98e8-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f98e8-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f98e8-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f98e8-108">See Also</span></span>  
 [<span data-ttu-id="f98e8-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f98e8-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f98e8-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f98e8-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f98e8-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="f98e8-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f98e8-112">break 语句</span><span class="sxs-lookup"><span data-stu-id="f98e8-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
 [<span data-ttu-id="f98e8-113">跳转语句</span><span class="sxs-lookup"><span data-stu-id="f98e8-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
