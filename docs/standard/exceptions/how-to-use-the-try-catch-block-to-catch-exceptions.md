---
title: 如何：使用 Try-Catch 块捕获异常
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5183a854ee2b7462ecc27786a5fc0697565194c0
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092743"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="c9a8c-102">如何使用 try/catch 块捕获异常</span><span class="sxs-lookup"><span data-stu-id="c9a8c-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="c9a8c-103">将可能引发异常的任何代码语句放置在 `try` 块中，将用于处理异常的语句放置在 `try` 块下的一个或多个 `catch` 块中。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-103">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="c9a8c-104">每个 `catch` 块包括异常类型，并且可以包含处理该异常类型所需的其他语句。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-104">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="c9a8c-105">在以下示例中，<xref:System.IO.StreamReader> 将打开一个名为 data.txt 的文件，并从文件中检索行。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-105">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="c9a8c-106">因为代码可能会引发任何三个异常，因此将其放置于 `try` 块中。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-106">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="c9a8c-107">三个 `catch` 块捕获异常并通过将结果向控制台显示来处理它们。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-107">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="c9a8c-108">公共语言运行时 (CLR) 会捕获未由 `catch` 块处理的异常。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-108">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="c9a8c-109">如果异常由 CLR 捕获，则可能出现以下结果之一，具体取决于 CLR 配置：</span><span class="sxs-lookup"><span data-stu-id="c9a8c-109">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="c9a8c-110">出现“调试”对话框。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-110">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="c9a8c-111">该程序停止执行，出现含有异常信息的对话框。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-111">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="c9a8c-112">错误输出到[标准错误输出流](xref:System.Console.Error)。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-112">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="c9a8c-113">大多数代码可能会引发异常，并且一些异常（如 <xref:System.OutOfMemoryException>）可能随时由 CLR 本身引发。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-113">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="c9a8c-114">虽然应用程序无需处理这些异常，但在编写供他人使用的库时，应注意到这种可能性。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-114">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="c9a8c-115">有关何时在 `try` 块中设置代码的建议，请参阅[异常的最佳做法](best-practices-for-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-115">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9a8c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a8c-116">See also</span></span>

[<span data-ttu-id="c9a8c-117">异常</span><span class="sxs-lookup"><span data-stu-id="c9a8c-117">Exceptions</span></span>](index.md)  
[<span data-ttu-id="c9a8c-118">处理 .NET 中的 I/O 错误</span><span class="sxs-lookup"><span data-stu-id="c9a8c-118">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
