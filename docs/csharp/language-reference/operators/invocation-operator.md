---
title: () 运算符 - C# 参考
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 3a0af33739c9cb4d090842219eba4ece9700ef89
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362777"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7fea6-102">() 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7fea6-102">() operator (C# Reference)</span></span>

<span data-ttu-id="7fea6-103">括号 `()` 通常用于方法或委托调用或用于强制转换表达式。</span><span class="sxs-lookup"><span data-stu-id="7fea6-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="7fea6-104">此外可以使用括号来指定表达式中计算操作的顺序。</span><span class="sxs-lookup"><span data-stu-id="7fea6-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="7fea6-105">有关详细信息，请参阅[运算符](../../programming-guide/statements-expressions-operators/operators.md)一文中的[添加括号](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses)部分。</span><span class="sxs-lookup"><span data-stu-id="7fea6-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="7fea6-106">对于按优先级排序的运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="7fea6-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="7fea6-107">方法调用</span><span class="sxs-lookup"><span data-stu-id="7fea6-107">Method invocation</span></span>

<span data-ttu-id="7fea6-108">下面的示例演示如何调用方法（带或不带参数）和委托：</span><span class="sxs-lookup"><span data-stu-id="7fea6-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="7fea6-109">在调用带 [`new`](../keywords/new-operator.md) 运算符的[构造函数](../../programming-guide/classes-and-structs/constructors.md)时，还可以使用括号。</span><span class="sxs-lookup"><span data-stu-id="7fea6-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="7fea6-110">有关这些方法的详细信息，请参阅[方法](../../programming-guide/classes-and-structs/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="7fea6-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="7fea6-111">有关委托的详细信息，请参阅[委托](../../programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7fea6-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="7fea6-112">强制转换表达式</span><span class="sxs-lookup"><span data-stu-id="7fea6-112">Cast expression</span></span>

<span data-ttu-id="7fea6-113">`(T)E` 形式的强制转换表达式调用转换运算符以将表达式 `E` 的值转换为类型 `T`。</span><span class="sxs-lookup"><span data-stu-id="7fea6-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="7fea6-114">如果不存在从类型 `E` 到类型 `T` 的显式转换，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="7fea6-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="7fea6-115">有关如何定义转换运算符的信息，请参阅[显式](../keywords/explicit.md)和[隐式](../keywords/implicit.md)关键字文章。</span><span class="sxs-lookup"><span data-stu-id="7fea6-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="7fea6-116">下面的示例演示了数值类型之间的类型转换：</span><span class="sxs-lookup"><span data-stu-id="7fea6-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="7fea6-117">若要详细了解数值类型之间的预定义显式转换，请参阅[显式数值转换表](../keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="7fea6-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="7fea6-118">有关详细信息，请参阅[强制转换和类型转换](../../programming-guide/types/casting-and-type-conversions.md)以及[转换运算符](../../programming-guide/statements-expressions-operators/conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="7fea6-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="7fea6-119">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="7fea6-119">Operator overloadability</span></span>

<span data-ttu-id="7fea6-120">不能重载 `()` 运算符。</span><span class="sxs-lookup"><span data-stu-id="7fea6-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7fea6-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7fea6-121">C# language specification</span></span>

<span data-ttu-id="7fea6-122">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [调用表达式](~/_csharplang/spec/expressions.md#invocation-expressions)和[强制转换表达式](~/_csharplang/spec/expressions.md#cast-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="7fea6-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fea6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fea6-123">See also</span></span>

- [<span data-ttu-id="7fea6-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7fea6-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7fea6-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7fea6-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7fea6-126">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="7fea6-126">C# Operators</span></span>](index.md)