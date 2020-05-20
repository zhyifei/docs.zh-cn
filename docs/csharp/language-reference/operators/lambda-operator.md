---
title: => 运算符 - C# 参考
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 15c02e11610866f359e3e3a7e2751ded918154b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846243"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8879a-102">=> 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8879a-102">=> operator (C# reference)</span></span>

<span data-ttu-id="8879a-103">`=>` 令牌支持两种形式：作为 [lambda 运算符](#lambda-operator)、作为成员名称的分隔符和[表达式主体定义](#expression-body-definition)中的成员实现。</span><span class="sxs-lookup"><span data-stu-id="8879a-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="8879a-104">lambda 运算符</span><span class="sxs-lookup"><span data-stu-id="8879a-104">Lambda operator</span></span>

<span data-ttu-id="8879a-105">在 [lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)中，lambda 运算符 `=>` 将左侧的输入参数与右侧的 lambda 主体分开。</span><span class="sxs-lookup"><span data-stu-id="8879a-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="8879a-106">以下示例使用带有方法语法的 [LINQ](../../programming-guide/concepts/linq/index.md) 功能来演示 lambda 表达式的用法：</span><span class="sxs-lookup"><span data-stu-id="8879a-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="8879a-107">lambda 表达式的输入参数在编译时是强类型。</span><span class="sxs-lookup"><span data-stu-id="8879a-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="8879a-108">当编译器可以推断输入参数的类型时，如前面的示例所示，可以省略类型声明。</span><span class="sxs-lookup"><span data-stu-id="8879a-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="8879a-109">如果需要指定输入参数的类型，则必须对每个参数执行类型声明，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8879a-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="8879a-110">以下示例显示如何在没有输入参数的情况下定义 lambda 表达式：</span><span class="sxs-lookup"><span data-stu-id="8879a-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="8879a-111">有关详细信息，请参阅 [Lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="8879a-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="8879a-112">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="8879a-112">Expression body definition</span></span>

<span data-ttu-id="8879a-113">表达式主体定义具有下列常规语法：</span><span class="sxs-lookup"><span data-stu-id="8879a-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="8879a-114">其中 `expression` 是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="8879a-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="8879a-115">`expression` 的返回类型必须可隐式转换为成员的返回类型。</span><span class="sxs-lookup"><span data-stu-id="8879a-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="8879a-116">如果成员的返回类型是 `void`，或者如果成员是构造函数、终结器或属性 `set` 访问器，则 `expression` 必须是[语句表达式](~/_csharplang/spec/statements.md#expression-statements)，其可以是任意类型。</span><span class="sxs-lookup"><span data-stu-id="8879a-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements), which can be of any type.</span></span>

<span data-ttu-id="8879a-117">以下示例演示了用于 `Person.ToString` 方法的表达式主体定义：</span><span class="sxs-lookup"><span data-stu-id="8879a-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="8879a-118">它是以下方法定义的简写版：</span><span class="sxs-lookup"><span data-stu-id="8879a-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="8879a-119">自 C#6 起，支持方法、运算符和只读属性的表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="8879a-119">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="8879a-120">自 C# 7.0 起，支持构造函数、终结器、属性和索引器访问器的表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="8879a-120">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="8879a-121">有关详细信息，请参阅 “[Expression-bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)”。</span><span class="sxs-lookup"><span data-stu-id="8879a-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8879a-122">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="8879a-122">Operator overloadability</span></span>

<span data-ttu-id="8879a-123">不能重载 `=>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="8879a-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8879a-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8879a-124">C# language specification</span></span>

<span data-ttu-id="8879a-125">有关 lambda 运算符的详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="8879a-125">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8879a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8879a-126">See also</span></span>

- [<span data-ttu-id="8879a-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8879a-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8879a-128">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="8879a-128">C# operators</span></span>](index.md)
