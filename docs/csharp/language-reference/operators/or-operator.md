---
title: '| 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312873"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d08b9-102">| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d08b9-102">| operator (C# Reference)</span></span>

<span data-ttu-id="d08b9-103">针对整型类型和 `bool` 预定义了二元 `|` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d08b9-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="d08b9-104">对于整型类型，`|` 会计算其操作数的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="d08b9-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="d08b9-105">对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d08b9-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d08b9-106">备注</span><span class="sxs-lookup"><span data-stu-id="d08b9-106">Remarks</span></span>

<span data-ttu-id="d08b9-107">二元 `|` 运算符计算两个操作数，无论第一个操作数的值是什么。这与[条件 OR 运算符](boolean-logical-operators.md#conditional-logical-or-operator-) `||` 相反。</span><span class="sxs-lookup"><span data-stu-id="d08b9-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||`.</span></span>

<span data-ttu-id="d08b9-108">用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="d08b9-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="d08b9-109">示例</span><span class="sxs-lookup"><span data-stu-id="d08b9-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="d08b9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d08b9-110">See also</span></span>

- [<span data-ttu-id="d08b9-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d08b9-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d08b9-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d08b9-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d08b9-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="d08b9-113">C# operators</span></span>](index.md)