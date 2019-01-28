---
title: goto 语句 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: e4642d0e43a538217493298b58d572e435db5dae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645322"
---
# <a name="goto-c-reference"></a><span data-ttu-id="94827-102">goto（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="94827-102">goto (C# Reference)</span></span>

<span data-ttu-id="94827-103">`goto` 语句将程序控制直接传递给标记语句。</span><span class="sxs-lookup"><span data-stu-id="94827-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="94827-104">`goto` 的一个通常用法是将控制传递给特定的 switch-case 标签或 `switch` 语句中的默认标签。</span><span class="sxs-lookup"><span data-stu-id="94827-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="94827-105">`goto` 语句还用于跳出深嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="94827-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="94827-106">示例</span><span class="sxs-lookup"><span data-stu-id="94827-106">Example</span></span>

<span data-ttu-id="94827-107">下面的示例演示了 `goto` 在 [switch](switch.md) 语句中的使用。</span><span class="sxs-lookup"><span data-stu-id="94827-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="94827-108">示例</span><span class="sxs-lookup"><span data-stu-id="94827-108">Example</span></span>

<span data-ttu-id="94827-109">下面的示例演示了使用 `goto` 跳出嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="94827-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="94827-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="94827-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="94827-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="94827-111">See also</span></span>

- [<span data-ttu-id="94827-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="94827-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="94827-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="94827-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="94827-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="94827-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="94827-115">goto 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="94827-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
- [<span data-ttu-id="94827-116">跳转语句</span><span class="sxs-lookup"><span data-stu-id="94827-116">Jump Statements</span></span>](jump-statements.md)
