---
title: default 运算符 - C# 参考
ms.custom: seodec18
description: 使用 default 运算符生成类型的默认值
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 5623cb9dc3790b5bb99635c41cb3f122f4c71d8e
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796936"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="37ddd-103">default 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="37ddd-103">default operator (C# reference)</span></span>

<span data-ttu-id="37ddd-104">`default` 运算符生成类型的[默认值](../keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="37ddd-104">The `default` operator produces the [default value](../keywords/default-values-table.md) of a type.</span></span> <span data-ttu-id="37ddd-105">`default` 运算符的实参必须是类型或类型形参的名称。</span><span class="sxs-lookup"><span data-stu-id="37ddd-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="37ddd-106">下面的示例演示 `default` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="37ddd-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="37ddd-107">还可以将 `default` 关键字用作 [`switch` 语句](../keywords/switch.md)中的默认用例标签。</span><span class="sxs-lookup"><span data-stu-id="37ddd-107">You also use the `default` keyword as the default case label within the [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="37ddd-108">default 文本</span><span class="sxs-lookup"><span data-stu-id="37ddd-108">default literal</span></span>

<span data-ttu-id="37ddd-109">从 C# 7.1 开始，当编译器可以推断表达式类型时，可以使用 `default` 文本生成类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="37ddd-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="37ddd-110">`default` 文本表达式生成与 `default(T)` 表达式（其中，`T` 是推断的类型）相同的值。</span><span class="sxs-lookup"><span data-stu-id="37ddd-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="37ddd-111">可以在以下任一情况下使用 `default` 文本：</span><span class="sxs-lookup"><span data-stu-id="37ddd-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="37ddd-112">对变量进行赋值或初始化时。</span><span class="sxs-lookup"><span data-stu-id="37ddd-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="37ddd-113">在声明可选方法参数的默认值时。</span><span class="sxs-lookup"><span data-stu-id="37ddd-113">In the declaration of the default value for an optional method parameter.</span></span>
- <span data-ttu-id="37ddd-114">在方法调用中提供参数值时。</span><span class="sxs-lookup"><span data-stu-id="37ddd-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="37ddd-115">在 `return` 语句中或作为表达式体成员中的表达式时。</span><span class="sxs-lookup"><span data-stu-id="37ddd-115">In a `return` statement or as an expression in an expression-bodied member.</span></span>

<span data-ttu-id="37ddd-116">下面的示例演示 `default` 文本的用法：</span><span class="sxs-lookup"><span data-stu-id="37ddd-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="37ddd-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="37ddd-117">C# language specification</span></span>

<span data-ttu-id="37ddd-118">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [默认值表达式](~/_csharplang/spec/expressions.md#default-value-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="37ddd-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="37ddd-119">有关 `default` 文本的详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)。</span><span class="sxs-lookup"><span data-stu-id="37ddd-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37ddd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="37ddd-120">See also</span></span>

- [<span data-ttu-id="37ddd-121">C# 参考</span><span class="sxs-lookup"><span data-stu-id="37ddd-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="37ddd-122">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="37ddd-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="37ddd-123">默认值表</span><span class="sxs-lookup"><span data-stu-id="37ddd-123">Default values table</span></span>](../keywords/default-values-table.md)
