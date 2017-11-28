---
title: "匿名函数（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 888743bb1c49df123b57b4d09e0251dbe1e049d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="b50f9-102">匿名函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b50f9-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="b50f9-103">匿名函数是一个“内联”语句或表达式，可在需要委托类型的任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="b50f9-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="b50f9-104">可以使用匿名函数来初始化命名委托，或传递命名委托（而不是命名委托类型）作为方法参数。</span><span class="sxs-lookup"><span data-stu-id="b50f9-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="b50f9-105">共有两种匿名函数，以下主题中分别讨论了这些函数：</span><span class="sxs-lookup"><span data-stu-id="b50f9-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
-   <span data-ttu-id="b50f9-106">[Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="b50f9-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
-   [<span data-ttu-id="b50f9-107">匿名方法</span><span class="sxs-lookup"><span data-stu-id="b50f9-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="b50f9-108">Lambda 表达式可以绑定到表达式树，也可以绑定到委托。</span><span class="sxs-lookup"><span data-stu-id="b50f9-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="b50f9-109">C# 中委托的发展</span><span class="sxs-lookup"><span data-stu-id="b50f9-109">The Evolution of Delegates in C#</span></span>  
 <span data-ttu-id="b50f9-110">在 C# 1.0 中，通过使用在代码中其他位置定义的方法显式初始化委托来创建委托的实例。</span><span class="sxs-lookup"><span data-stu-id="b50f9-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="b50f9-111">C# 2.0 引入了匿名方法的概念，作为一种编写可在委托调用中执行的未命名内联语句块的方式。</span><span class="sxs-lookup"><span data-stu-id="b50f9-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="b50f9-112">C# 3.0 引入了 lambda 表达式，这种表达式与匿名方法的概念类似，但更具表现力并且更简练。</span><span class="sxs-lookup"><span data-stu-id="b50f9-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="b50f9-113">这两个功能统称为*匿名函数*。</span><span class="sxs-lookup"><span data-stu-id="b50f9-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="b50f9-114">通常，面向 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 及更高版本的应用程序应使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="b50f9-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="b50f9-115">下面的示例演示从 C# 1.0 到 C# 3.0 委托创建过程的发展：</span><span class="sxs-lookup"><span data-stu-id="b50f9-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b50f9-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b50f9-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b50f9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b50f9-117">See Also</span></span>  
 [<span data-ttu-id="b50f9-118">语句、表达式和运算符</span><span class="sxs-lookup"><span data-stu-id="b50f9-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
 [<span data-ttu-id="b50f9-119">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="b50f9-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="b50f9-120">委托</span><span class="sxs-lookup"><span data-stu-id="b50f9-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="b50f9-121">表达式树</span><span class="sxs-lookup"><span data-stu-id="b50f9-121">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
