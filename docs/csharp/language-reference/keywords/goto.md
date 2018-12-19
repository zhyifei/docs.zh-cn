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
ms.openlocfilehash: bfc997631cc147bf5718ec91a57e2995cead052f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236760"
---
# <a name="goto-c-reference"></a><span data-ttu-id="7eb6b-102">goto（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7eb6b-102">goto (C# Reference)</span></span>

<span data-ttu-id="7eb6b-103">`goto` 语句将程序控制直接传递给标记语句。</span><span class="sxs-lookup"><span data-stu-id="7eb6b-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="7eb6b-104">`goto` 的一个通常用法是将控制传递给特定的 switch-case 标签或 `switch` 语句中的默认标签。</span><span class="sxs-lookup"><span data-stu-id="7eb6b-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="7eb6b-105">`goto` 语句还用于跳出深嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="7eb6b-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="7eb6b-106">示例</span><span class="sxs-lookup"><span data-stu-id="7eb6b-106">Example</span></span>

<span data-ttu-id="7eb6b-107">下面的示例演示了 `goto` 在 [switch](switch.md) 语句中的使用。</span><span class="sxs-lookup"><span data-stu-id="7eb6b-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="7eb6b-108">示例</span><span class="sxs-lookup"><span data-stu-id="7eb6b-108">Example</span></span>

<span data-ttu-id="7eb6b-109">下面的示例演示了使用 `goto` 跳出嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="7eb6b-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="7eb6b-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7eb6b-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7eb6b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7eb6b-111">See also</span></span>

- [<span data-ttu-id="7eb6b-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7eb6b-112">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="7eb6b-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7eb6b-113">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="7eb6b-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="7eb6b-114">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="7eb6b-115">goto 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="7eb6b-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)  
- [<span data-ttu-id="7eb6b-116">跳转语句</span><span class="sxs-lookup"><span data-stu-id="7eb6b-116">Jump Statements</span></span>](jump-statements.md)  
