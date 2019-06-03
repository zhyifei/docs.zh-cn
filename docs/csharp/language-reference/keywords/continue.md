---
title: continue 语句 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: d5fd2f5edf85c3ac2c8f0367b85b37e76e2e856e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422107"
---
# <a name="continue-c-reference"></a><span data-ttu-id="56852-102">continue（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="56852-102">continue (C# Reference)</span></span>

<span data-ttu-id="56852-103">`continue` 语句将控制传递到其中出现的封闭 [while](../../../csharp/language-reference/keywords/while.md)、[do](../../../csharp/language-reference/keywords/do.md)、[for](../../../csharp/language-reference/keywords/for.md) 或 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="56852-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="56852-104">示例</span><span class="sxs-lookup"><span data-stu-id="56852-104">Example</span></span>

<span data-ttu-id="56852-105">在本示例中，计数器最初是从 1 到 10 进行计数。</span><span class="sxs-lookup"><span data-stu-id="56852-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="56852-106">通过结合使用 `continue` 语句和表达式 `(i < 9)`，跳过 `continue` 和 `for` 主体末尾之间的语句。</span><span class="sxs-lookup"><span data-stu-id="56852-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="56852-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="56852-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="56852-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="56852-108">See also</span></span>

- [<span data-ttu-id="56852-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="56852-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="56852-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="56852-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="56852-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="56852-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="56852-112">break 语句</span><span class="sxs-lookup"><span data-stu-id="56852-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
