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
ms.openlocfilehash: 74d166dbcf03b868baf464864e4c246f789df9cc
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605869"
---
# <a name="continue-c-reference"></a><span data-ttu-id="21d3c-102">continue（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="21d3c-102">continue (C# Reference)</span></span>

<span data-ttu-id="21d3c-103">`continue` 语句将控制传递到其中出现的封闭 [while](./while.md)、[do](./do.md)、[for](./for.md) 或 [foreach](./foreach-in.md) 语句的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="21d3c-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="21d3c-104">示例</span><span class="sxs-lookup"><span data-stu-id="21d3c-104">Example</span></span>

<span data-ttu-id="21d3c-105">在本示例中，计数器最初是从 1 到 10 进行计数。</span><span class="sxs-lookup"><span data-stu-id="21d3c-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="21d3c-106">通过结合使用 `continue` 语句和表达式 `(i < 9)`，跳过 `continue` 和 `for` 主体末尾之间的语句。</span><span class="sxs-lookup"><span data-stu-id="21d3c-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="21d3c-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="21d3c-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="21d3c-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="21d3c-108">See also</span></span>

- [<span data-ttu-id="21d3c-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="21d3c-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21d3c-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="21d3c-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21d3c-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="21d3c-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="21d3c-112">break 语句</span><span class="sxs-lookup"><span data-stu-id="21d3c-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
