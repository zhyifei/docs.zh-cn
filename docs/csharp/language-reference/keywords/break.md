---
title: break 语句（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 9dc71cce3cc0ca4035df483d2b3a3ab9a3bab9c5
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46695823"
---
# <a name="break-c-reference"></a><span data-ttu-id="7e417-102">break（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7e417-102">break (C# Reference)</span></span>

<span data-ttu-id="7e417-103">`break` 语句将终止其所在位置的最接近封闭循环或 [switch](../../../csharp/language-reference/keywords/switch.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="7e417-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="7e417-104">控制权将传递给已终止语句后面的语句（若有）。</span><span class="sxs-lookup"><span data-stu-id="7e417-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="7e417-105">示例</span><span class="sxs-lookup"><span data-stu-id="7e417-105">Example</span></span>

<span data-ttu-id="7e417-106">在此示例中，条件语句包含一个应从 1 计数到 100 的计数器；但 `break` 语句在计数器计数到 4 后终止了循环。</span><span class="sxs-lookup"><span data-stu-id="7e417-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="7e417-107">示例</span><span class="sxs-lookup"><span data-stu-id="7e417-107">Example</span></span>

<span data-ttu-id="7e417-108">在此示例中，`break` 语句用于中断内层嵌套循环，并将控制权返回给外层循环。</span><span class="sxs-lookup"><span data-stu-id="7e417-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="7e417-109">示例</span><span class="sxs-lookup"><span data-stu-id="7e417-109">Example</span></span>

<span data-ttu-id="7e417-110">本示例演示 `break` 在 [switch](../../../csharp/language-reference/keywords/switch.md) 语句中的用法。</span><span class="sxs-lookup"><span data-stu-id="7e417-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="7e417-111">如果输入 `4`，则输出为：</span><span class="sxs-lookup"><span data-stu-id="7e417-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="7e417-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7e417-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7e417-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e417-113">See Also</span></span>

- [<span data-ttu-id="7e417-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7e417-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7e417-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7e417-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7e417-116">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="7e417-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="7e417-117">switch</span><span class="sxs-lookup"><span data-stu-id="7e417-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)  
- [<span data-ttu-id="7e417-118">跳转语句</span><span class="sxs-lookup"><span data-stu-id="7e417-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)  
- [<span data-ttu-id="7e417-119">迭代语句</span><span class="sxs-lookup"><span data-stu-id="7e417-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
