---
title: 如何：使用 Finally 块
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 213ab53c68a37ac0ba5f337a1d6fc32bfe6f8989
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45618212"
---
# <a name="how-to-use-finally-blocks"></a><span data-ttu-id="6ba2d-102">如何使用 finally 块</span><span class="sxs-lookup"><span data-stu-id="6ba2d-102">How to use finally blocks</span></span>

<span data-ttu-id="6ba2d-103">发生异常时，将停止执行且会向相应异常处理程序赋予控制权。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-103">When an exception occurs, execution stops and control is given to the appropriate exception handler.</span></span> <span data-ttu-id="6ba2d-104">这意味着会绕过预计要执行的代码行。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-104">This often means that lines of code you expect to be executed are bypassed.</span></span> <span data-ttu-id="6ba2d-105">即使引发了异常，也需要完成某些资源清理，例如关闭文件。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-105">Some resource cleanup, such as closing a file, needs to be done even if an exception is thrown.</span></span> <span data-ttu-id="6ba2d-106">若要执行此操作，可以使用 `finally` 块。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-106">To do this, you can use a `finally` block.</span></span> <span data-ttu-id="6ba2d-107">无论是否引发异常，始终会执行 `finally` 块。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-107">A `finally` block always executes, regardless of whether an exception is thrown.</span></span>

<span data-ttu-id="6ba2d-108">下方代码示例使用 `try`/`catch` 块来捕获 <xref:System.ArgumentOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-108">The following code example uses a `try`/`catch` block to catch an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="6ba2d-109">`Main` 方法会创建两个数组，并尝试将一个数组复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-109">The `Main` method creates two arrays and attempts to copy one to the other.</span></span> <span data-ttu-id="6ba2d-110">该操作将生成 <xref:System.ArgumentOutOfRangeException> 并且会向控制台写入错误。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-110">The action generates an <xref:System.ArgumentOutOfRangeException> and the error is written to the console.</span></span> <span data-ttu-id="6ba2d-111">`finally` 块执行时不考虑复制操作的结果。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-111">The `finally` block executes regardless of the outcome of the copy action.</span></span>

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="6ba2d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ba2d-112">See also</span></span>

- [<span data-ttu-id="6ba2d-113">异常</span><span class="sxs-lookup"><span data-stu-id="6ba2d-113">Exceptions</span></span>](index.md)
