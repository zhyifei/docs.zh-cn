---
title: 使用实现 IDisposable 的对象
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25c5ffa89e6ce4e589b8f12a7b8518272426c9e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597785"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="c9754-102">使用实现 IDisposable 的对象</span><span class="sxs-lookup"><span data-stu-id="c9754-102">Using objects that implement IDisposable</span></span>

<span data-ttu-id="c9754-103">公共语言运行时的垃圾回收器回收托管对象使用的内存，而使用非托管资源的类型则实现 <xref:System.IDisposable> 接口，以允许回收分配给这些非托管资源的内存。</span><span class="sxs-lookup"><span data-stu-id="c9754-103">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the memory allocated to these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="c9754-104">在使用完实现 <xref:System.IDisposable> 的对象后，应调用该对象的 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 实现。</span><span class="sxs-lookup"><span data-stu-id="c9754-104">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="c9754-105">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="c9754-105">You can do this in one of two ways:</span></span>  
  
* <span data-ttu-id="c9754-106">使用 C# `using` 语句或 Visual Basic `Using` 语句。</span><span class="sxs-lookup"><span data-stu-id="c9754-106">With the C# `using` statement or the Visual Basic `Using` statement.</span></span>  
  
* <span data-ttu-id="c9754-107">实现 `try/finally` 块。</span><span class="sxs-lookup"><span data-stu-id="c9754-107">By implementing a `try/finally` block.</span></span>  

## <a name="the-using-statement"></a><span data-ttu-id="c9754-108">using 语句</span><span class="sxs-lookup"><span data-stu-id="c9754-108">The using statement</span></span>

<span data-ttu-id="c9754-109">C# 中的 `using` 语句和 Visual Basic 中的 `Using` 语句可以简化创建和清理对象而必须编写的代码。</span><span class="sxs-lookup"><span data-stu-id="c9754-109">The `using` statement in C# and the `Using` statement in Visual Basic simplify the code that you must write to create and clean up an object.</span></span> <span data-ttu-id="c9754-110">`using` 语句获取一个或多个资源，执行指定的语句，并自动处置对象。</span><span class="sxs-lookup"><span data-stu-id="c9754-110">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="c9754-111">但是，`using` 语句仅对在用于构造对象的方法的范围内使用的对象有用。</span><span class="sxs-lookup"><span data-stu-id="c9754-111">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>  
  
<span data-ttu-id="c9754-112">以下示例使用 `using` 语句创建并发布 <xref:System.IO.StreamReader?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="c9754-112">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
<span data-ttu-id="c9754-113">请注意，虽然 <xref:System.IO.StreamReader> 类实现 <xref:System.IDisposable> 接口（这指示使用非托管资源），但此示例不显式调用 <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9754-113">Note that although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c9754-114">当 C# 或 Visual Basic 编译器遇到 `using` 语句时，它会发出与以下显式包含 `try/finally` 块的代码等效的中间语言 (IL)。</span><span class="sxs-lookup"><span data-stu-id="c9754-114">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
<span data-ttu-id="c9754-115">使用 C# `using` 语句，还可以在一个语句（在内部相当于嵌套语句 `using`）中获取多个资源。</span><span class="sxs-lookup"><span data-stu-id="c9754-115">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="c9754-116">下面的示例实例化两个 <xref:System.IO.StreamReader> 对象以读取两个不同文件的内容。</span><span class="sxs-lookup"><span data-stu-id="c9754-116">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="c9754-117">Try/finally 块</span><span class="sxs-lookup"><span data-stu-id="c9754-117">Try/finally block</span></span>

<span data-ttu-id="c9754-118">可以选择直接实现 `try/finally` 块，而不是将 `try/finally` 块包装在 `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="c9754-118">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="c9754-119">这可以是私有编码样式，或者你可能出于下列原因之一需要这样做：</span><span class="sxs-lookup"><span data-stu-id="c9754-119">This may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>  
  
* <span data-ttu-id="c9754-120">包含 `catch` 块可处理 `try` 块中引发的任何异常。</span><span class="sxs-lookup"><span data-stu-id="c9754-120">To include a `catch` block to handle any exceptions thrown in the `try` block.</span></span> <span data-ttu-id="c9754-121">否则，不会处理 `using` 语句引发的任何异常，`using` 块中引发的任何异常也是如此，前提是 `try/catch` 块不存在。</span><span class="sxs-lookup"><span data-stu-id="c9754-121">Otherwise, any exceptions thrown by the `using` statement are unhandled, as are any exceptions thrown within the `using` block if a `try/catch` block isn't present.</span></span>  
  
* <span data-ttu-id="c9754-122">实例化实现 <xref:System.IDisposable>（其范围对于声明它的块是非本地的）的对象。</span><span class="sxs-lookup"><span data-stu-id="c9754-122">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>  
  
<span data-ttu-id="c9754-123">下面的示例与上一示例类似，不同之处在于此示例使用 `try/catch/finally` 块实例化、使用和清理 <xref:System.IO.StreamReader> 对象，同时处理 <xref:System.IO.StreamReader> 构造函数及其 <xref:System.IO.StreamReader.ReadToEnd%2A> 方法抛出的任何异常。</span><span class="sxs-lookup"><span data-stu-id="c9754-123">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="c9754-124">请注意，`finally` 块中的代码检查实现 <xref:System.IDisposable> 的对象在其调用 `null` 方法之前不为 <xref:System.IDisposable.Dispose%2A>。</span><span class="sxs-lookup"><span data-stu-id="c9754-124">Note that the code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="c9754-125">此操作失败会导致运行时发生 <xref:System.NullReferenceException> 异常。</span><span class="sxs-lookup"><span data-stu-id="c9754-125">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
<span data-ttu-id="c9754-126">如果选择实现或必须实现 `try/finally` 块，可以遵循此基本模式，因为编程语言不支持 `using` 语句，但允许直接调用 <xref:System.IDisposable.Dispose%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9754-126">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c9754-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9754-127">See also</span></span>

- <span data-ttu-id="c9754-128">[清理未托管资源](../../../docs/standard/garbage-collection/unmanaged.md)（清理未托管资源）</span><span class="sxs-lookup"><span data-stu-id="c9754-128">[Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)</span></span>
- [<span data-ttu-id="c9754-129">using 语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c9754-129">using Statement (C# Reference)</span></span>](~/docs/csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="c9754-130">Using 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9754-130">Using Statement (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/statements/using-statement.md)
