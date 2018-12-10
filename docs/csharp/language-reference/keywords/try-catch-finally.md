---
title: try-catch-finally（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 18625838bd36d9d32079b7c72ded7ed660b8cf3a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130658"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="d8253-102">try-catch-finally（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d8253-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="d8253-103">`catch` 和 `finally` 的常见用法是获得并使用 `try` 块中的资源、处理 `catch` 块中的异常情况，以及释放 `finally` 块中的资源。</span><span class="sxs-lookup"><span data-stu-id="d8253-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="d8253-104">有关重新引发异常的详细信息和示例，请参阅 [try-catch](try-catch.md) 和[引发异常](../../../standard/exceptions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d8253-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="d8253-105">有关 `finally` 块的详细信息，请参阅 [try-finally](try-finally.md)。</span><span class="sxs-lookup"><span data-stu-id="d8253-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="d8253-106">示例</span><span class="sxs-lookup"><span data-stu-id="d8253-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="d8253-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="d8253-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d8253-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8253-108">See also</span></span>

- [<span data-ttu-id="d8253-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d8253-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d8253-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d8253-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d8253-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="d8253-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d8253-112">try、throw 和 catch 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="d8253-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="d8253-113">异常处理语句</span><span class="sxs-lookup"><span data-stu-id="d8253-113">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="d8253-114">throw</span><span class="sxs-lookup"><span data-stu-id="d8253-114">throw</span></span>](throw.md)
- [<span data-ttu-id="d8253-115">如何显式引发异常</span><span class="sxs-lookup"><span data-stu-id="d8253-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="d8253-116">using 语句</span><span class="sxs-lookup"><span data-stu-id="d8253-116">using Statement</span></span>](using-statement.md)