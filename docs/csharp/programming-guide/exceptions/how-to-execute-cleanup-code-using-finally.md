---
title: 如何：使用 finally 执行清理代码（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 948281af45d04714ed6fc308b60341e87abeb830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331703"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="893f4-102">如何：使用 finally 执行清理代码（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="893f4-102">How to: Execute Cleanup Code Using finally (C# Programming Guide)</span></span>
<span data-ttu-id="893f4-103">`finally` 语句的用途是确保立即进行对象（通常是容纳外部资源的对象）的必要清理（即使引发异常）。</span><span class="sxs-lookup"><span data-stu-id="893f4-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="893f4-104">这类清理的一个示例是在使用之后立即对 <xref:System.IO.FileStream> 调用 <xref:System.IO.Stream.Close%2A>（而不是等待公共语言运行时对对象进行垃圾回收），如下所示：</span><span class="sxs-lookup"><span data-stu-id="893f4-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="893f4-105">示例</span><span class="sxs-lookup"><span data-stu-id="893f4-105">Example</span></span>  
 <span data-ttu-id="893f4-106">若要将上面的代码转换为 `try-catch-finally` 语句，可将清理代码与工作代码分开，如下所示。</span><span class="sxs-lookup"><span data-stu-id="893f4-106">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 <span data-ttu-id="893f4-107">因为可能会在 `try` 块中进行 `OpenWrite()` 调用之前的任何时候发生异常，或 `OpenWrite()` 调用本身可能会失败，所以我们不保证在尝试关闭文件时文件处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="893f4-107">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="893f4-108">`finally` 块添加了一个检查，以便在调用 <xref:System.IO.Stream.Close%2A> 方法之前确保 <xref:System.IO.FileStream> 对象不是 `null`。</span><span class="sxs-lookup"><span data-stu-id="893f4-108">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="893f4-109">如果不进行 `null` 检查，则 `finally` 块可能会引发自己的 <xref:System.NullReferenceException>，但是在可能时应避免在 `finally` 块中引发异常。</span><span class="sxs-lookup"><span data-stu-id="893f4-109">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="893f4-110">数据库连接是在 `finally` 块中进行关闭的另一个很好的候选项。</span><span class="sxs-lookup"><span data-stu-id="893f4-110">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="893f4-111">因为与数据库服务器之间的允许连接数有时会受到限制，所以应尽快关闭数据库连接。</span><span class="sxs-lookup"><span data-stu-id="893f4-111">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="893f4-112">如果在可以关闭连接之前引发异常，则这是使用 `finally` 块比等待垃圾回收更好的另一种情况。</span><span class="sxs-lookup"><span data-stu-id="893f4-112">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893f4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="893f4-113">See Also</span></span>  
 [<span data-ttu-id="893f4-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="893f4-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="893f4-115">异常和异常处理</span><span class="sxs-lookup"><span data-stu-id="893f4-115">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
 [<span data-ttu-id="893f4-116">异常处理</span><span class="sxs-lookup"><span data-stu-id="893f4-116">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)  
 [<span data-ttu-id="893f4-117">using 语句</span><span class="sxs-lookup"><span data-stu-id="893f4-117">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
 [<span data-ttu-id="893f4-118">try-catch</span><span class="sxs-lookup"><span data-stu-id="893f4-118">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="893f4-119">try-finally</span><span class="sxs-lookup"><span data-stu-id="893f4-119">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="893f4-120">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="893f4-120">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
