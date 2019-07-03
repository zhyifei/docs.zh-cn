---
title: => 运算符 - C# 参考
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: a7fea9810cb02269278638ec71cd106463b029e9
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025023"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b5ad7-102">=> 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b5ad7-102">=> operator (C# reference)</span></span>

<span data-ttu-id="b5ad7-103">`=>` 令牌支持两种形式：作为 lambda 运算符、作为成员名称的分隔符和表达式主体定义中的成员实现。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="b5ad7-104">lambda 运算符</span><span class="sxs-lookup"><span data-stu-id="b5ad7-104">Lambda operator</span></span>

<span data-ttu-id="b5ad7-105">在 [lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)中，lambda 运算符`=>`将左侧的输入变量与右侧的 lambda 主体分开。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="b5ad7-106">以下示例使用带有方法语法的 [LINQ](../../programming-guide/concepts/linq/index.md) 功能来演示 lambda 表达式的用法：</span><span class="sxs-lookup"><span data-stu-id="b5ad7-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="b5ad7-107">lambda 表达式的输入变量在编译时是强类型。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="b5ad7-108">当编译器可以推断输入变量的类型时，如前面的示例所示，可以省略类型声明。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="b5ad7-109">如果需要指定输入变量的类型，则必须对每个变量执行此操作，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="b5ad7-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="b5ad7-110">以下示例显示如何在没有输入变量的情况下定义 lambda 表达式：</span><span class="sxs-lookup"><span data-stu-id="b5ad7-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="b5ad7-111">有关详细信息，请参阅 [Lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="b5ad7-112">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="b5ad7-112">Expression body definition</span></span>

<span data-ttu-id="b5ad7-113">表达式主体定义具有下列常规语法：</span><span class="sxs-lookup"><span data-stu-id="b5ad7-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="b5ad7-114">其中“expression”  是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="b5ad7-115">请注意，仅当成员的返回类型是 `void` 时，或者成员是构造函数、终结器或属性 `set` 访问器时，表达式才可能是语句表达式   。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="b5ad7-116">以下示例演示了用于 `Person.ToString` 方法的表达式主体定义：</span><span class="sxs-lookup"><span data-stu-id="b5ad7-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="b5ad7-117">它是以下方法定义的简写版：</span><span class="sxs-lookup"><span data-stu-id="b5ad7-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="b5ad7-118">自 C#6 起支持方法和只读属性的表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="b5ad7-119">自 C# 7.0 起支持构造函数、终结器、属性访问器和索引器的表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="b5ad7-120">有关详细信息，请参阅 [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)（Expression-bodied 成员）。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="b5ad7-121">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="b5ad7-121">Operator overloadability</span></span>

<span data-ttu-id="b5ad7-122">不能重载 `=>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b5ad7-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b5ad7-123">C# language specification</span></span>

<span data-ttu-id="b5ad7-124">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="b5ad7-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ad7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5ad7-125">See also</span></span>

- [<span data-ttu-id="b5ad7-126">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b5ad7-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b5ad7-127">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="b5ad7-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="b5ad7-128">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="b5ad7-128">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="b5ad7-129">Expression-Bodied 成员</span><span class="sxs-lookup"><span data-stu-id="b5ad7-129">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)
