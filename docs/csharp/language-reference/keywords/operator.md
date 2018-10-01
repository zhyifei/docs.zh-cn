---
title: 运算符关键字（C# 参考）
description: 了解如何重载内置 C# 运算符
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 1e11d7767b61becc39b1158fae9cb2abe997e4bd
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47209367"
---
# <a name="operator-c-reference"></a><span data-ttu-id="95961-103">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="95961-103">operator (C# Reference)</span></span>

<span data-ttu-id="95961-104">使用 `operator` 关键字重载内置运算符，或在类或结构声明中提供用户定义的转换。</span><span class="sxs-lookup"><span data-stu-id="95961-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="95961-105">若要在自定义类或结构上重载运算符，可以在相应的类型中创建运算符声明。</span><span class="sxs-lookup"><span data-stu-id="95961-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="95961-106">重载内置 C# 运算符的运算符声明必须满足以下规则：</span><span class="sxs-lookup"><span data-stu-id="95961-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="95961-107">同时包含 `public` 和 `static` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="95961-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="95961-108">包含 `operator X`，其中 `X` 是被重载运算符的名称或符号。</span><span class="sxs-lookup"><span data-stu-id="95961-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="95961-109">一元运算符具有一个参数，二元运算符具有两个参数。</span><span class="sxs-lookup"><span data-stu-id="95961-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="95961-110">在每种情况下，都必须至少有一个参数与声明运算符的类或结构的类型相同。</span><span class="sxs-lookup"><span data-stu-id="95961-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="95961-111">有关如何定义转换运算符的信息，请参阅[显式](explicit.md)和[隐式](implicit.md)关键字文章。</span><span class="sxs-lookup"><span data-stu-id="95961-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="95961-112">有关可重载 C# 运算符的概述，请参阅[可重载运算符](../../programming-guide/statements-expressions-operators/overloadable-operators.md)一文。</span><span class="sxs-lookup"><span data-stu-id="95961-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="95961-113">示例</span><span class="sxs-lookup"><span data-stu-id="95961-113">Example</span></span>

<span data-ttu-id="95961-114">以下示例定义了表示小数的 `Fraction` 类型。</span><span class="sxs-lookup"><span data-stu-id="95961-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="95961-115">此类重载 `+` 和 `*` 运算符以执行分数加法和乘法，并提供转换运算符将 `Fraction` 类型转换为 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="95961-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="95961-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="95961-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="95961-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="95961-117">See also</span></span>

- [<span data-ttu-id="95961-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="95961-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="95961-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="95961-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="95961-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="95961-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="95961-121">implicit</span><span class="sxs-lookup"><span data-stu-id="95961-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="95961-122">explicit</span><span class="sxs-lookup"><span data-stu-id="95961-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="95961-123">可重载运算符</span><span class="sxs-lookup"><span data-stu-id="95961-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="95961-124">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="95961-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
