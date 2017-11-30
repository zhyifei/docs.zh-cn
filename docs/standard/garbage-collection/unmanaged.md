---
title: "清理非托管资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c94a449edbbe38c4028e27fd946b66a054badf51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cleaning-up-unmanaged-resources"></a><span data-ttu-id="24b0c-102">清理非托管资源</span><span class="sxs-lookup"><span data-stu-id="24b0c-102">Cleaning Up Unmanaged Resources</span></span>
<span data-ttu-id="24b0c-103">对于你的应用程序创建的对象的大多数，你可以依赖于。NET 的垃圾回收器来处理内存管理。</span><span class="sxs-lookup"><span data-stu-id="24b0c-103">For the majority of the objects that your app creates, you can rely on .NET's garbage collector to handle memory management.</span></span> <span data-ttu-id="24b0c-104">但是，如果创建包括非托管资源的对象，则当你在应用中使用完非托管资源后，必须显式释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-104">However, when you create objects that include unmanaged resources, you must explicitly release those resources when you finish using them in your app.</span></span> <span data-ttu-id="24b0c-105">最常用的非托管资源类型是包装操作系统资源的对象，如文件、窗口、网络连接或数据库连接。</span><span class="sxs-lookup"><span data-stu-id="24b0c-105">The most common types of unmanaged resource are objects that wrap operating system resources, such as files, windows, network connections, or database connections.</span></span> <span data-ttu-id="24b0c-106">虽然垃圾回收器可以跟踪封装非托管资源的对象的生存期，但无法了解如何发布并清理这些非托管资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-106">Although the garbage collector is able to track the lifetime of an object that encapsulates an unmanaged resource, it doesn't know how to release and clean up the unmanaged resource.</span></span>  
  
 <span data-ttu-id="24b0c-107">如果你的类型使用非托管资源，则应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="24b0c-107">If your types use unmanaged resources, you should do the following:</span></span>  
  
-   <span data-ttu-id="24b0c-108">实现[释放模式](../../../docs/standard/design-guidelines/dispose-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="24b0c-108">Implement the [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md).</span></span> <span data-ttu-id="24b0c-109">这要求你提供 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 实现以启用非托管资源的确定性释放。</span><span class="sxs-lookup"><span data-stu-id="24b0c-109">This requires that you provide an <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation to enable the deterministic release of  unmanaged resources.</span></span> <span data-ttu-id="24b0c-110">当不再需要此对象（或其使用的资源）时，类型使用者可调用 <xref:System.IDisposable.Dispose%2A>。</span><span class="sxs-lookup"><span data-stu-id="24b0c-110">A consumer of your type calls <xref:System.IDisposable.Dispose%2A> when the object (and the resources it uses) is no longer needed.</span></span> <span data-ttu-id="24b0c-111"><xref:System.IDisposable.Dispose%2A> 方法立即释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-111">The <xref:System.IDisposable.Dispose%2A> method immediately releases the unmanaged resources.</span></span>  
  
-   <span data-ttu-id="24b0c-112">在类型使用者忘记调用 <xref:System.IDisposable.Dispose%2A> 的情况下，准备释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-112">Provide for your unmanaged resources to be released in the event that a consumer of your type forgets to call <xref:System.IDisposable.Dispose%2A>.</span></span> <span data-ttu-id="24b0c-113">有两种方法可以实现此目的：</span><span class="sxs-lookup"><span data-stu-id="24b0c-113">There are two ways to do this:</span></span>  
  
    -   <span data-ttu-id="24b0c-114">使用安全句柄包装非托管资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-114">Use a safe handle to wrap your unmanaged resource.</span></span> <span data-ttu-id="24b0c-115">这是推荐采用的方法。</span><span class="sxs-lookup"><span data-stu-id="24b0c-115">This is the recommended technique.</span></span> <span data-ttu-id="24b0c-116">安全句柄派生自 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 类并包含可靠的 <xref:System.Object.Finalize%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="24b0c-116">Safe handles are derived from the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class and include a robust <xref:System.Object.Finalize%2A> method.</span></span> <span data-ttu-id="24b0c-117">在使用安全句柄时，只需实现 <xref:System.IDisposable> 接口并在 <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> 实现中调用安全句柄的 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="24b0c-117">When you use a safe handle, you simply implement the <xref:System.IDisposable> interface and call your safe handle's <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> method in your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="24b0c-118">如果未调用安全句柄的 <xref:System.IDisposable.Dispose%2A> 方法，则垃圾回收器将自动调用安全句柄的终结器。</span><span class="sxs-lookup"><span data-stu-id="24b0c-118">The safe handle's finalizer is called automatically by the garbage collector if its <xref:System.IDisposable.Dispose%2A> method is not called.</span></span>  
  
         <span data-ttu-id="24b0c-119">- 或 -</span><span class="sxs-lookup"><span data-stu-id="24b0c-119">—or—</span></span>  
  
    -   <span data-ttu-id="24b0c-120">重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="24b0c-120">Override the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="24b0c-121">当类型使用者无法调用 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 以确定性地释放非托管资源时，终止会启用对非托管资源的非确定性释放。</span><span class="sxs-lookup"><span data-stu-id="24b0c-121">Finalization enables the non-deterministic release of unmanaged resources when the consumer of a type fails to call <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> to dispose of them deterministically.</span></span> <span data-ttu-id="24b0c-122">但是，由于对象终止是一项复杂且易出错的操作，建议你使用安全句柄而不是提供你自己的终结器。</span><span class="sxs-lookup"><span data-stu-id="24b0c-122">However, because object finalization can be a complex and error-prone operation, we recommend that you use a safe handle instead of providing your own finalizer.</span></span>  
  
 <span data-ttu-id="24b0c-123">然后，类型使用者可直接调用 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 实现以释放非托管资源使用的内存。</span><span class="sxs-lookup"><span data-stu-id="24b0c-123">Consumers of your type can then call your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation directly to free memory used by unmanaged resources.</span></span> <span data-ttu-id="24b0c-124">在正确实现 <xref:System.IDisposable.Dispose%2A> 方法时，安全句柄的 <xref:System.Object.Finalize%2A> 方法或 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 方法的重写会在未调用 <xref:System.IDisposable.Dispose%2A> 方法的情况下阻止清理资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-124">When you properly implement a <xref:System.IDisposable.Dispose%2A> method, either your safe handle's <xref:System.Object.Finalize%2A> method or your own override of the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method becomes a safeguard to clean up resources in the event that the <xref:System.IDisposable.Dispose%2A> method is not called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24b0c-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="24b0c-125">In This Section</span></span>  
 [<span data-ttu-id="24b0c-126">实现 Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="24b0c-126">Implementing a Dispose Method</span></span>](../../../docs/standard/garbage-collection/implementing-dispose.md)  
 <span data-ttu-id="24b0c-127">描述如何实现[释放模式](../../../docs/standard/design-guidelines/dispose-pattern.md)用于释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="24b0c-127">Describes how to implement the [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) for releasing unmanaged resources.</span></span>  
  
 [<span data-ttu-id="24b0c-128">使用实现 IDisposable 的对象</span><span class="sxs-lookup"><span data-stu-id="24b0c-128">Using Objects That Implement IDisposable</span></span>](../../../docs/standard/garbage-collection/using-objects.md)  
 <span data-ttu-id="24b0c-129">描述类型使用者如何确保调用其 <xref:System.IDisposable.Dispose%2A> 实现。</span><span class="sxs-lookup"><span data-stu-id="24b0c-129">Describes how consumers of a type ensure that its <xref:System.IDisposable.Dispose%2A> implementation is called.</span></span> <span data-ttu-id="24b0c-130">建议使用 C# `using` 语句或 Visual Basic `Using` 语句来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="24b0c-130">We recommend using the C# `using` statement or the Visual Basic `Using` statement to do this.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="24b0c-131">参考</span><span class="sxs-lookup"><span data-stu-id="24b0c-131">Reference</span></span>  
 <xref:System.IDisposable?displayProperty=nameWithType>  
 <span data-ttu-id="24b0c-132">定义用于释放非托管资源的 <xref:System.IDisposable.Dispose%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="24b0c-132">Defines the <xref:System.IDisposable.Dispose%2A> method for releasing unmanaged resources.</span></span>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 <span data-ttu-id="24b0c-133">如果 <xref:System.IDisposable.Dispose%2A> 方法未释放非托管资源，则准备对象终止。</span><span class="sxs-lookup"><span data-stu-id="24b0c-133">Provides for object finalization if unmanaged resources are not released by the <xref:System.IDisposable.Dispose%2A> method.</span></span>  
  
 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>  
 <span data-ttu-id="24b0c-134">取消终止。</span><span class="sxs-lookup"><span data-stu-id="24b0c-134">Suppresses finalization.</span></span> <span data-ttu-id="24b0c-135">通常，从 `Dispose` 方法调用此方法来阻止执行终结器。</span><span class="sxs-lookup"><span data-stu-id="24b0c-135">This method is customarily called from a `Dispose` method to prevent a finalizer from executing.</span></span>
