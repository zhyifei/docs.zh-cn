---
title: '! （null 包容）运算符 - C# 参考'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: cf941e5e3fa3fc6313ef8b2ff5c176aec68c1e6b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291679"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="c8b1e-103">!</span><span class="sxs-lookup"><span data-stu-id="c8b1e-103">!</span></span> <span data-ttu-id="c8b1e-104">（null 包容）运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c8b1e-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="c8b1e-105">在 C# 8.0 及更高版本中可用，一元后缀 `!` 运算符是 null 包容运算符。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="c8b1e-106">在已启用的[可为空的注释上下文](../../nullable-references.md#nullable-annotation-context)中，可以使用 null 包容运算符来声明可为空的引用类型的表达式 `x` 不为 null：`x!`。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't null: `x!`.</span></span> <span data-ttu-id="c8b1e-107">一元前缀 `!` 运算符是[逻辑非运算符](boolean-logical-operators.md#logical-negation-operator-)。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-107">The unary prefix `!` operator is a [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="c8b1e-108">null 包容运算符在运行时不起作用。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="c8b1e-109">它仅通过更改表达式的 null 状态来影响编译器的静态流分析。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="c8b1e-110">在运行时，表达式 `x!` 的计算结果为基础表达式 `x` 的结果。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="c8b1e-111">有关可为空引用类型特性的详细信息，请参见[可为空引用类型](../../nullable-references.md)。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-111">For more information about the nullable reference types feature, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="examples"></a><span data-ttu-id="c8b1e-112">示例</span><span class="sxs-lookup"><span data-stu-id="c8b1e-112">Examples</span></span>

<span data-ttu-id="c8b1e-113">null 包容运算符的一个用例是测试参数验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="c8b1e-114">例如，请考虑以下类：</span><span class="sxs-lookup"><span data-stu-id="c8b1e-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="c8b1e-115">使用 [ 测试框架](../../../core/testing/unit-testing-with-mstest.md)，可以在构造函数中为验证逻辑创建以下测试：</span><span class="sxs-lookup"><span data-stu-id="c8b1e-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="c8b1e-116">如果不使用 null 包容运算符，编译器将为前面的代码生成以下警告：`Warning CS8625: Cannot convert null literal to non-nullable reference type`。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="c8b1e-117">通过使用 null 包容运算符，可以让编译器知道传递 `null` 是预期行为，不应发出警告。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-117">With the use of the null-forgiving operator, you let the compiler know that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="c8b1e-118">如果你明确知道某个表达式不能为 `null`，但编译器无法识别它，也可以使用 null 包容运算符。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="c8b1e-119">在下面的示例中，如果 `IsValid` 方法返回 `true`，则其参数不是 `null`，可以放心取消对它的引用：</span><span class="sxs-lookup"><span data-stu-id="c8b1e-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="c8b1e-120">如果没有 null 包容运算符，编译器将为 `p.Name` 代码生成以下警告：`Warning CS8602: Dereference of a possibly null reference.`。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference.`.</span></span>

<span data-ttu-id="c8b1e-121">如果可以修改 `IsValid` 方法，则可使用 [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) 属性让编译器知道，当方法返回 `true` 时，`IsValid` 方法的参数不能是 `null`：</span><span class="sxs-lookup"><span data-stu-id="c8b1e-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to let the compiler know that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="c8b1e-122">在前面的例子中，不需要使用 null 包容运算符，因为编译器有足够的信息来发现 `p` 不能是 `if` 语句中的 `null`。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="c8b1e-123">如需深入了解允许你指定有关变量 null 状态的其他信息的属性，请参阅[使用属性升级 API 以定义 null 期望值](../../nullable-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="c8b1e-123">For more information about the attributes that allow you to specify additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8b1e-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8b1e-124">See also</span></span>

- [<span data-ttu-id="c8b1e-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c8b1e-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c8b1e-126">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c8b1e-126">C# operators</span></span>](index.md)
- [<span data-ttu-id="c8b1e-127">教程：使用可为空引用类型进行设计</span><span class="sxs-lookup"><span data-stu-id="c8b1e-127">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
