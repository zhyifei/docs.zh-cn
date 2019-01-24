---
title: '! 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 6b6d1796032f536aac0be49d4f101c1380b4e98f
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333221"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="41ae5-103">!</span><span class="sxs-lookup"><span data-stu-id="41ae5-103">!</span></span> <span data-ttu-id="41ae5-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="41ae5-104">operator (C# Reference)</span></span>

<span data-ttu-id="41ae5-105">逻辑非运算符 (`!`) 是一种否定其操作数的一元运算符。</span><span class="sxs-lookup"><span data-stu-id="41ae5-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="41ae5-106">它针对 `bool` 定义，当且仅当其操作数为 `false` 时返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="41ae5-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="41ae5-107">备注</span><span class="sxs-lookup"><span data-stu-id="41ae5-107">Remarks</span></span>

<span data-ttu-id="41ae5-108">用户定义的类型可以重载 `!` 运算符（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="41ae5-108">User-defined types can overload the `!` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="41ae5-109">示例</span><span class="sxs-lookup"><span data-stu-id="41ae5-109">Example</span></span>

[!code-csharp[csRefOperators#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#7)]

## <a name="see-also"></a><span data-ttu-id="41ae5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="41ae5-110">See also</span></span>

- [<span data-ttu-id="41ae5-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="41ae5-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="41ae5-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="41ae5-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="41ae5-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="41ae5-113">C# Operators</span></span>](index.md)