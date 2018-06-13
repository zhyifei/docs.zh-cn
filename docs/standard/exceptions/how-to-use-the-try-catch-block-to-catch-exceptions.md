---
title: 如何：使用 Try-Catch 块捕获异常
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b169353752f6e6483a056cdc9dd8c3227b9ebeb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571444"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="9efc3-102">如何使用 try/catch 块捕获异常</span><span class="sxs-lookup"><span data-stu-id="9efc3-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="9efc3-103">将可能引发异常的代码部分置于 `try` 块，将可处理异常的代码置于 `catch` 块。</span><span class="sxs-lookup"><span data-stu-id="9efc3-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="9efc3-104">`catch` 块是一系列以关键字 `catch` 开头的语句，后跟要执行的异常类型和操作。</span><span class="sxs-lookup"><span data-stu-id="9efc3-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="9efc3-105">下方代码示例使用 `try`/`catch` 块来捕获可能的异常。</span><span class="sxs-lookup"><span data-stu-id="9efc3-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="9efc3-106">`Main` 方法包含带有 <xref:System.IO.StreamReader> 语句的 `try` 块，此块可打开名为 `data.txt` 的数据文件，并写入该文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="9efc3-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="9efc3-107">以下 `try` 块是可捕获由 `try` 块导致的任何异常的 `catch` 块。</span><span class="sxs-lookup"><span data-stu-id="9efc3-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="9efc3-108">公共语言运行时可捕获未被 catch 块捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="9efc3-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="9efc3-109">会出现调试对话框，或是停止运行程序且会出现含有异常信息的对话框，或者会将错误打印到 STDERR，具体情况取决于运行时的配置方式。</span><span class="sxs-lookup"><span data-stu-id="9efc3-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="9efc3-110">几乎任何代码行都可能导致异常，尤其是由公共语言运行时本身造成的异常，如 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="9efc3-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="9efc3-111">大多数应用程序无需处理这些异常，但在编写供他人使用的库时，应注意到这种可能性。</span><span class="sxs-lookup"><span data-stu-id="9efc3-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="9efc3-112">有关何时在 try 块中设置代码的建议，请参阅[异常的最佳做法](best-practices-for-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="9efc3-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9efc3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9efc3-113">See Also</span></span>  
[<span data-ttu-id="9efc3-114">异常</span><span class="sxs-lookup"><span data-stu-id="9efc3-114">Exceptions</span></span>](index.md)
