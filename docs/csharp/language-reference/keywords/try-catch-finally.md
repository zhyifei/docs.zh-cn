---
title: "try-catch-finally（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0861cdb6a08c9ada9c6903be536b1fd5eef16579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="f81a6-102">try-catch-finally（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f81a6-102">try-catch-finally (C# Reference)</span></span>
<span data-ttu-id="f81a6-103">`catch` 和 `finally` 的常见用法是获得并使用 `try` 块中的资源、处理 `catch` 块中的异常情况，以及释放 `finally` 块中的资源。</span><span class="sxs-lookup"><span data-stu-id="f81a6-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>  
  
 <span data-ttu-id="f81a6-104">有关重新引发异常的详细信息和示例，请参阅 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 和[引发异常](../../../standard/exceptions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f81a6-104">For more information and examples on re-throwing exceptions, see [try-catch](../../../csharp/language-reference/keywords/try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="f81a6-105">有关 `finally` 块的详细信息，请参阅 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)。</span><span class="sxs-lookup"><span data-stu-id="f81a6-105">For more information about the `finally` block, see [try-finally](../../../csharp/language-reference/keywords/try-finally.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f81a6-106">示例</span><span class="sxs-lookup"><span data-stu-id="f81a6-106">Example</span></span>  
 [!code-csharp[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f81a6-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f81a6-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f81a6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f81a6-108">See Also</span></span>  
 [<span data-ttu-id="f81a6-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f81a6-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f81a6-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f81a6-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f81a6-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="f81a6-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f81a6-112">try、throw 和 catch 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="f81a6-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [<span data-ttu-id="f81a6-113">异常处理语句</span><span class="sxs-lookup"><span data-stu-id="f81a6-113">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="f81a6-114">throw</span><span class="sxs-lookup"><span data-stu-id="f81a6-114">throw</span></span>](../../../csharp/language-reference/keywords/throw.md)  
 [<span data-ttu-id="f81a6-115">如何显式引发异常</span><span class="sxs-lookup"><span data-stu-id="f81a6-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)  
 [<span data-ttu-id="f81a6-116">using 语句</span><span class="sxs-lookup"><span data-stu-id="f81a6-116">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
