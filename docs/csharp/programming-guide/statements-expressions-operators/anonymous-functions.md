---
title: 匿名函数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 4d266584e1867a512e4b61e8839fe948aafb007f
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363924"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="b6279-102">匿名函数 -（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b6279-102">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="b6279-103">匿名函数是一个“内联”语句或表达式，可在需要委托类型的任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="b6279-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="b6279-104">可以使用匿名函数来初始化命名委托，或传递命名委托（而不是命名委托类型）作为方法参数。</span><span class="sxs-lookup"><span data-stu-id="b6279-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="b6279-105">可以使用 [lambda 表达式](lambda-expressions.md)或[匿名方法](../../language-reference/operators/delegate-operator.md)来创建匿名函数。</span><span class="sxs-lookup"><span data-stu-id="b6279-105">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="b6279-106">建议使用 lambda 表达式，因为它们提供了更简洁和富有表现力的方式来编写内联代码。</span><span class="sxs-lookup"><span data-stu-id="b6279-106">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="b6279-107">与匿名方法不同，某些类型的 lambda 表达式可以转换为表达式树类型。</span><span class="sxs-lookup"><span data-stu-id="b6279-107">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="b6279-108">C\# 中委托的演变</span><span class="sxs-lookup"><span data-stu-id="b6279-108">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="b6279-109">在 C# 1.0 中，通过使用在代码中其他位置定义的方法显式初始化委托来创建委托的实例。</span><span class="sxs-lookup"><span data-stu-id="b6279-109">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="b6279-110">C# 2.0 引入了匿名方法的概念，作为一种编写可在委托调用中执行的未命名内联语句块的方式。</span><span class="sxs-lookup"><span data-stu-id="b6279-110">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="b6279-111">C# 3.0 引入了 lambda 表达式，这种表达式与匿名方法的概念类似，但更具表现力并且更简练。</span><span class="sxs-lookup"><span data-stu-id="b6279-111">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="b6279-112">这两个功能统称为*匿名函数*。</span><span class="sxs-lookup"><span data-stu-id="b6279-112">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="b6279-113">通常，面向 .NET Framework 3.5 及更高版本的应用程序应使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="b6279-113">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="b6279-114">下面的示例演示从 C# 1.0 到 C# 3.0 委托创建过程的发展：</span><span class="sxs-lookup"><span data-stu-id="b6279-114">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b6279-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b6279-115">C# language specification</span></span>

<span data-ttu-id="b6279-116">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="b6279-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6279-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6279-117">See also</span></span>

- [<span data-ttu-id="b6279-118">语句、表达式和运算符</span><span class="sxs-lookup"><span data-stu-id="b6279-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="b6279-119">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="b6279-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="b6279-120">委托</span><span class="sxs-lookup"><span data-stu-id="b6279-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="b6279-121">表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="b6279-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
