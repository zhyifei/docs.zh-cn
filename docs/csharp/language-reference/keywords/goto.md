---
title: goto 语句（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: d4fd9f1f26b82b409d704c45e4bcf18cceef8282
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507518"
---
# <a name="goto-c-reference"></a><span data-ttu-id="1e4f7-102">goto（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1e4f7-102">goto (C# Reference)</span></span>

<span data-ttu-id="1e4f7-103">`goto` 语句将程序控制直接传递给标记语句。</span><span class="sxs-lookup"><span data-stu-id="1e4f7-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="1e4f7-104">`goto` 的一个通常用法是将控制传递给特定的 switch-case 标签或 `switch` 语句中的默认标签。</span><span class="sxs-lookup"><span data-stu-id="1e4f7-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="1e4f7-105">`goto` 语句还用于跳出深嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="1e4f7-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="1e4f7-106">示例</span><span class="sxs-lookup"><span data-stu-id="1e4f7-106">Example</span></span>

<span data-ttu-id="1e4f7-107">下面的示例演示了 `goto` 在 [switch](switch.md) 语句中的使用。</span><span class="sxs-lookup"><span data-stu-id="1e4f7-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="1e4f7-108">示例</span><span class="sxs-lookup"><span data-stu-id="1e4f7-108">Example</span></span>

<span data-ttu-id="1e4f7-109">下面的示例演示了使用 `goto` 跳出嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="1e4f7-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="1e4f7-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1e4f7-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1e4f7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e4f7-111">See also</span></span>

- [<span data-ttu-id="1e4f7-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1e4f7-112">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="1e4f7-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1e4f7-113">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="1e4f7-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="1e4f7-114">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="1e4f7-115">goto 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="1e4f7-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)  
- [<span data-ttu-id="1e4f7-116">跳转语句</span><span class="sxs-lookup"><span data-stu-id="1e4f7-116">Jump Statements</span></span>](jump-statements.md)  
