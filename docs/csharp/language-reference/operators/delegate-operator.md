---
title: 委托运算符 - C# 参考
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1fe281776bd75d8fa869065cd24e85f04fec849d
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331826"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="5b407-102">委托运算符 -（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5b407-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="5b407-103">`delegate` 运算符创建一个可以转换为委托类型的匿名方法：</span><span class="sxs-lookup"><span data-stu-id="5b407-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

<span data-ttu-id="5b407-104">从 C# 3 开始，[lambda表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)提供了一种更简洁和富有表现力的方式来创建匿名函数。</span><span class="sxs-lookup"><span data-stu-id="5b407-104">Beginning with C# 3, [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="5b407-105">使用 [=> 运算符](lambda-operator.md)构造 lambda 表达式：</span><span class="sxs-lookup"><span data-stu-id="5b407-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>

[!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]

<span data-ttu-id="5b407-106">使用 `delegate` 运算符时，可以省略参数列表。</span><span class="sxs-lookup"><span data-stu-id="5b407-106">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="5b407-107">如果这样做，可以将创建的匿名方法转换为具有任何参数列表的委托类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5b407-107">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="5b407-108">这是 lambda 表达式不支持的匿名方法的唯一功能。</span><span class="sxs-lookup"><span data-stu-id="5b407-108">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="5b407-109">在所有其他情况下，lambda 表达式是编写内联代码的首选方法。</span><span class="sxs-lookup"><span data-stu-id="5b407-109">In all other cases, a lambda expression is a preferred way to write inline code.</span></span> <span data-ttu-id="5b407-110">有关 lambda 表达式功能的更多信息（例如，如何捕获外部变量），请参阅 [lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="5b407-110">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="5b407-111">还可以使用 `delegate` 关键字声明[委托类型](../builtin-types/reference-types.md#the-delegate-type)。</span><span class="sxs-lookup"><span data-stu-id="5b407-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5b407-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5b407-112">C# language specification</span></span>

<span data-ttu-id="5b407-113">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="5b407-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b407-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b407-114">See also</span></span>

- [<span data-ttu-id="5b407-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5b407-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5b407-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5b407-116">C# operators</span></span>](index.md)
