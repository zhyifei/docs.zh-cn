---
title: try-catch-finally - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 787005ec09a2c5c4f0e5033c83fd6a7ab7875b7e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422165"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="b7c86-102">try-catch-finally（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b7c86-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="b7c86-103">`catch` 和 `finally` 的常见用法是获得并使用 `try` 块中的资源、处理 `catch` 块中的异常情况，以及释放 `finally` 块中的资源。</span><span class="sxs-lookup"><span data-stu-id="b7c86-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="b7c86-104">有关重新引发异常的详细信息和示例，请参阅 [try-catch](try-catch.md) 和[引发异常](../../../standard/exceptions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c86-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="b7c86-105">有关 `finally` 块的详细信息，请参阅 [try-finally](try-finally.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c86-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="b7c86-106">示例</span><span class="sxs-lookup"><span data-stu-id="b7c86-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="b7c86-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b7c86-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b7c86-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7c86-108">See also</span></span>

- [<span data-ttu-id="b7c86-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b7c86-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b7c86-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b7c86-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b7c86-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="b7c86-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b7c86-112">try、throw 和 catch 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="b7c86-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="b7c86-113">throw</span><span class="sxs-lookup"><span data-stu-id="b7c86-113">throw</span></span>](throw.md)
- [<span data-ttu-id="b7c86-114">如何：显式抛出异常</span><span class="sxs-lookup"><span data-stu-id="b7c86-114">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="b7c86-115">using 语句</span><span class="sxs-lookup"><span data-stu-id="b7c86-115">using Statement</span></span>](using-statement.md)
