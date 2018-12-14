---
title: unchecked 关键字（C# 引用）
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: 301e054c627ae7fc9a07c55c9d2b9a7738b9fb73
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146694"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="fdc4a-102">unchecked（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fdc4a-102">unchecked (C# Reference)</span></span>

<span data-ttu-id="fdc4a-103">`unchecked` 关键字用于取消整型类型的算术运算和转换的溢出检查。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="fdc4a-104">在未经检查的上下文中，如果表达式生成的值超出目标类型的范围，则不会标记溢出。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="fdc4a-105">例如，由于以下示例中的计算在 `unchecked` 块或表达式中执行，因此将忽略计算结果对于整数而言过大的事实，并且向 `int1` 赋予值 -2,147,483,639。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="fdc4a-106">如果删除 `unchecked` 环境，会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="fdc4a-107">由于表达式的所有项都是常量，因此可在编译时检测到溢出。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="fdc4a-108">在编译时和运行时，默认不检查包含非常数项的表达式。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="fdc4a-109">请参阅[启用检查](checked.md)，获取有关使用启用了检查的环境的信息。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-109">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="fdc4a-110">由于检查溢出需要时间，因此在没有溢出风险的情况下使用取消检查的代码可能会提高性能。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="fdc4a-111">但是，如果存在溢出的可能，则应使用启用了检查的环境。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-111">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="fdc4a-112">示例</span><span class="sxs-lookup"><span data-stu-id="fdc4a-112">Example</span></span>

<span data-ttu-id="fdc4a-113">此示例演示如何使用 `unchecked`关键字。</span><span class="sxs-lookup"><span data-stu-id="fdc4a-113">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="fdc4a-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fdc4a-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fdc4a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc4a-115">See also</span></span>

- [<span data-ttu-id="fdc4a-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fdc4a-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="fdc4a-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fdc4a-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fdc4a-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="fdc4a-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fdc4a-119">Checked and Unchecked</span><span class="sxs-lookup"><span data-stu-id="fdc4a-119">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="fdc4a-120">checked</span><span class="sxs-lookup"><span data-stu-id="fdc4a-120">checked</span></span>](checked.md)