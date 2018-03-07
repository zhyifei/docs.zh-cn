---
title: "实现 Dispose 方法"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 404fdece284accf305ef3cf2324be2e37a8da4b6
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2018
---
# <a name="implementing-a-dispose-method"></a><span data-ttu-id="46f46-102">实现 Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="46f46-102">Implementing a Dispose method</span></span>

<span data-ttu-id="46f46-103">通过实现 <xref:System.IDisposable.Dispose%2A> 方法来释放应用程序使用的非托管资源。</span><span class="sxs-lookup"><span data-stu-id="46f46-103">You implement a <xref:System.IDisposable.Dispose%2A> method to release unmanaged resources used by your application.</span></span> <span data-ttu-id="46f46-104">.NET 垃圾回收器不分配或释放非托管内存。</span><span class="sxs-lookup"><span data-stu-id="46f46-104">The .NET garbage collector does not allocate or release unmanaged memory.</span></span>  
  
<span data-ttu-id="46f46-105">对象清理模式（称为[清理模式](../../../docs/standard/design-guidelines/dispose-pattern.md)）对对象生存期强制施加顺序。</span><span class="sxs-lookup"><span data-stu-id="46f46-105">The pattern for disposing an object, referred to as a [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md), imposes order on the lifetime of an object.</span></span> <span data-ttu-id="46f46-106">释放模式仅用于访问非托管资源的对象，如文件和管道句柄、注册表句柄、等待句柄或指向非托管内存块的指针。</span><span class="sxs-lookup"><span data-stu-id="46f46-106">The dispose pattern is used only for objects that access unmanaged resources, such as file and pipe handles, registry handles, wait handles, or pointers to blocks of unmanaged memory.</span></span> <span data-ttu-id="46f46-107">这是因为垃圾回收器在回收不使用的托管对象时非常高效，但无法回收非托管对象。</span><span class="sxs-lookup"><span data-stu-id="46f46-107">This is because the garbage collector is very efficient at reclaiming unused managed objects, but it is unable to reclaim unmanaged objects.</span></span>  
  
<span data-ttu-id="46f46-108">释放模式有两种变体：</span><span class="sxs-lookup"><span data-stu-id="46f46-108">The dispose pattern has two variations:</span></span>  
  
* <span data-ttu-id="46f46-109">你包装类型在安全句柄中（即，在从 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 派生的类中）使用的每个非托管资源。</span><span class="sxs-lookup"><span data-stu-id="46f46-109">You wrap each unmanaged resource that a type uses in a safe handle (that is, in a class derived from <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>).</span></span> <span data-ttu-id="46f46-110">在这种情况下，你可以实现 <xref:System.IDisposable> 接口和额外的 `Dispose(Boolean)` 方法。</span><span class="sxs-lookup"><span data-stu-id="46f46-110">In this case, you implement the <xref:System.IDisposable> interface and an additional `Dispose(Boolean)` method.</span></span> <span data-ttu-id="46f46-111">这是建议的变体，不要求重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="46f46-111">This is the recommended variation and doesn't require overriding the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span>  
  
  > [!NOTE]
  > <span data-ttu-id="46f46-112"><xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> 命名空间提供了一组派生自 <xref:System.Runtime.InteropServices.SafeHandle> 的类，[使用安全句柄](#SafeHandles)部分中列出了这些类。</span><span class="sxs-lookup"><span data-stu-id="46f46-112">The <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> namespace provides a set of classes derived from <xref:System.Runtime.InteropServices.SafeHandle>, which are listed in the [Using safe handles](#SafeHandles) section.</span></span> <span data-ttu-id="46f46-113">如果找不到适用于释放非托管资源的类，则可实现你自己的 <xref:System.Runtime.InteropServices.SafeHandle> 的子类。</span><span class="sxs-lookup"><span data-stu-id="46f46-113">If you can't find a class that is suitable for releasing your unmanaged resource, you can implement your own subclass of <xref:System.Runtime.InteropServices.SafeHandle>.</span></span>  
  
* <span data-ttu-id="46f46-114">你可以实现 <xref:System.IDisposable> 接口和额外的 `Dispose(Boolean)` 方法，还可以重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="46f46-114">You implement the <xref:System.IDisposable> interface and an additional `Dispose(Boolean)` method, and you also override the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46f46-115">如果类型的使用者未调用你的 <xref:System.Object.Finalize%2A> 实现，则必须重写 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 以确保释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="46f46-115">You must override <xref:System.Object.Finalize%2A> to ensure that unmanaged resources are disposed of if your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation is not called by a consumer of your type.</span></span> <span data-ttu-id="46f46-116">如果使用上一项目符号中讨论的推荐方法，则 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 类可代表你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="46f46-116">If you use the recommended technique discussed in the previous bullet, the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class does this on your behalf.</span></span>  
  
<span data-ttu-id="46f46-117">若要帮助确保始终正确地清理资源，<xref:System.IDisposable.Dispose%2A> 方法应该可以多次调用而不引发异常。</span><span class="sxs-lookup"><span data-stu-id="46f46-117">To help ensure that resources are always cleaned up appropriately, a <xref:System.IDisposable.Dispose%2A> method should be callable multiple times without throwing an exception.</span></span>  
  
<span data-ttu-id="46f46-118">为 <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> 方法提供的代码示例演示了强行垃圾回收如何在回收对象的成员仍在执行时引起终结器运行。</span><span class="sxs-lookup"><span data-stu-id="46f46-118">The code example provided for the <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> method shows how aggressive garbage collection can cause a finalizer to run while a member of the reclaimed object is still executing.</span></span> <span data-ttu-id="46f46-119">在较长的 <xref:System.GC.KeepAlive%2A> 方法末尾最好调用 <xref:System.IDisposable.Dispose%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="46f46-119">It is a good idea to call the <xref:System.GC.KeepAlive%2A> method at the end of a lengthy <xref:System.IDisposable.Dispose%2A> method.</span></span>  
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a><span data-ttu-id="46f46-120">Dispose() 和 Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="46f46-120">Dispose() and Dispose(Boolean)</span></span>  

<span data-ttu-id="46f46-121"><xref:System.IDisposable> 接口需要实现单个无参数的方法 <xref:System.IDisposable.Dispose%2A>。</span><span class="sxs-lookup"><span data-stu-id="46f46-121">The <xref:System.IDisposable> interface requires the implementation of a single parameterless method, <xref:System.IDisposable.Dispose%2A>.</span></span> <span data-ttu-id="46f46-122">但是，释放模式需要实现两种 `Dispose` 方法：</span><span class="sxs-lookup"><span data-stu-id="46f46-122">However, the dispose pattern requires two `Dispose` methods to be implemented:</span></span>  
  
* <span data-ttu-id="46f46-123">一种没有参数的公共非虚拟的（Visual Basic 中的 `NonInheritable`）<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 实现。</span><span class="sxs-lookup"><span data-stu-id="46f46-123">A public non-virtual (`NonInheritable` in Visual Basic) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation that has no parameters.</span></span>  
  
* <span data-ttu-id="46f46-124">受保护的虚拟（Visual Basic 中的`Overridable`）`Dispose` 方法，其签名为：</span><span class="sxs-lookup"><span data-stu-id="46f46-124">A protected virtual (`Overridable` in Visual Basic) `Dispose` method whose signature is:</span></span>  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a><span data-ttu-id="46f46-125">Dispose() 重载</span><span class="sxs-lookup"><span data-stu-id="46f46-125">The Dispose() overload</span></span>

<span data-ttu-id="46f46-126">由于公共、非虚拟的（Visual Basic 中的 `NonInheritable`）、无参数 `Dispose` 方法由该类型的使用者调用，因此其用途是释放非托管资源和指示终结器（如果存在）不必运行。</span><span class="sxs-lookup"><span data-stu-id="46f46-126">Because the public, non-virtual (`NonInheritable` in Visual Basic), parameterless `Dispose` method is called by a consumer of the type, its purpose is to free unmanaged resources and to indicate that the finalizer, if one is present, doesn't have to run.</span></span> <span data-ttu-id="46f46-127">因此，它具有标准实现：</span><span class="sxs-lookup"><span data-stu-id="46f46-127">Because of this, it has a standard implementation:</span></span>  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
<span data-ttu-id="46f46-128">`Dispose` 方法执行所有对象清理，使垃圾回收器不再需要调用对象的 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 重写。</span><span class="sxs-lookup"><span data-stu-id="46f46-128">The `Dispose` method performs all object cleanup, so the garbage collector no longer needs to call the objects' <xref:System.Object.Finalize%2A?displayProperty=nameWithType> override.</span></span> <span data-ttu-id="46f46-129">因此，调用 <xref:System.GC.SuppressFinalize%2A> 方法会阻止垃圾回收器运行终结器。</span><span class="sxs-lookup"><span data-stu-id="46f46-129">Therefore, the call to the <xref:System.GC.SuppressFinalize%2A> method prevents the garbage collector from running the finalizer.</span></span> <span data-ttu-id="46f46-130">如果类型没有终结器，则对 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> 的调用不起作用。</span><span class="sxs-lookup"><span data-stu-id="46f46-130">If the type has no finalizer, the call to <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> has no effect.</span></span> <span data-ttu-id="46f46-131">请注意，释放非托管资源的实际工作是通过第二次重载 `Dispose` 方法执行的。</span><span class="sxs-lookup"><span data-stu-id="46f46-131">Note that the actual work of releasing unmanaged resources is performed by the second overload of the `Dispose` method.</span></span>  
  
### <a name="the-disposeboolean-overload"></a><span data-ttu-id="46f46-132">Dispose(Boolean) 重载</span><span class="sxs-lookup"><span data-stu-id="46f46-132">The Dispose(Boolean) overload</span></span>

<span data-ttu-id="46f46-133">在第二个重载中，disposing 参数是 <xref:System.Boolean>，用于指明方法调用是来自 <xref:System.IDisposable.Dispose%2A> 方法（值为 `true`），还是来自终结器（值为 `false`）。</span><span class="sxs-lookup"><span data-stu-id="46f46-133">In the second overload, the *disposing* parameter is a <xref:System.Boolean> that indicates whether the method call comes from a <xref:System.IDisposable.Dispose%2A> method (its value is `true`) or from a finalizer (its value is `false`).</span></span>  
  
<span data-ttu-id="46f46-134">方法的主体包含两个代码块：</span><span class="sxs-lookup"><span data-stu-id="46f46-134">The body of the method consists of two blocks of code:</span></span>  
  
* <span data-ttu-id="46f46-135">释放非托管资源的块。</span><span class="sxs-lookup"><span data-stu-id="46f46-135">A block that frees unmanaged resources.</span></span> <span data-ttu-id="46f46-136">无论 `disposing` 参数的值如何，都会执行此块。</span><span class="sxs-lookup"><span data-stu-id="46f46-136">This block executes regardless of the value of the `disposing` parameter.</span></span>  
  
* <span data-ttu-id="46f46-137">释放托管资源的条件块。</span><span class="sxs-lookup"><span data-stu-id="46f46-137">A conditional block that frees managed resources.</span></span> <span data-ttu-id="46f46-138">如果 `disposing` 的值为 `true`，则执行此块。</span><span class="sxs-lookup"><span data-stu-id="46f46-138">This block executes if the value of `disposing` is `true`.</span></span> <span data-ttu-id="46f46-139">它释放的托管资源可包括：</span><span class="sxs-lookup"><span data-stu-id="46f46-139">The managed resources that it frees can include:</span></span>  
  
  <span data-ttu-id="46f46-140">**实现 <xref:System.IDisposable> 的托管对象。**</span><span class="sxs-lookup"><span data-stu-id="46f46-140">**Managed objects that implement <xref:System.IDisposable>.**</span></span> <span data-ttu-id="46f46-141">可用于调用其 <xref:System.IDisposable.Dispose%2A> 实现的条件块。</span><span class="sxs-lookup"><span data-stu-id="46f46-141">The conditional block can be used to call their <xref:System.IDisposable.Dispose%2A> implementation.</span></span> <span data-ttu-id="46f46-142">如果你已使用安全句柄来包装非托管资源，则应在此处调用 <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> 实现。</span><span class="sxs-lookup"><span data-stu-id="46f46-142">If you have used a safe handle to wrap your unmanaged resource, you should call the <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> implementation here.</span></span>  
  
  <span data-ttu-id="46f46-143">**占用大量内存或使用短缺资源的托管对象。**</span><span class="sxs-lookup"><span data-stu-id="46f46-143">**Managed objects that consume large amounts of memory or consume scarce resources.**</span></span> <span data-ttu-id="46f46-144">在 `Dispose` 方法中显式释放这些对象的速度快于垃圾回收器不确定性回收它们的速度。</span><span class="sxs-lookup"><span data-stu-id="46f46-144">Freeing these objects explicitly in the `Dispose` method releases them faster than if they were reclaimed non-deterministically by the garbage collector.</span></span>  
  
<span data-ttu-id="46f46-145">如果方法调用来自终结器（即当 disposing 为 `false`），则仅执行释放非托管资源的代码。</span><span class="sxs-lookup"><span data-stu-id="46f46-145">If the method call comes from a finalizer (that is, if *disposing* is `false`), only the code that frees unmanaged resources executes.</span></span> <span data-ttu-id="46f46-146">由于未定义垃圾回收器在终止期间销毁托管对象的顺序，因此使用 `Dispose` 的值调用此 `false` 重载将阻止终结器尝试释放可能已被回收的托管资源。</span><span class="sxs-lookup"><span data-stu-id="46f46-146">Because the order in which the garbage collector destroys managed objects during finalization is not defined, calling this `Dispose` overload with a value of `false` prevents the finalizer from trying to release managed resources that may have already been reclaimed.</span></span>  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a><span data-ttu-id="46f46-147">实现基类的释放模式</span><span class="sxs-lookup"><span data-stu-id="46f46-147">Implementing the dispose pattern for a base class</span></span>

<span data-ttu-id="46f46-148">如果实现基类的释放模式，则必须提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="46f46-148">If you implement the dispose pattern for a base class, you must provide the following:</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="46f46-149">你应针对实现 <xref:System.IDisposable.Dispose> 并且不是 `sealed`（Visual Basic 中的 `NotInheritable`）的所有基类实现此模式。</span><span class="sxs-lookup"><span data-stu-id="46f46-149">You should implement this pattern for all base classes that implement <xref:System.IDisposable.Dispose> and are not `sealed` (`NotInheritable` in Visual Basic).</span></span>  
  
* <span data-ttu-id="46f46-150">调用 <xref:System.IDisposable.Dispose%2A> 方法的 `Dispose(Boolean)` 实现。</span><span class="sxs-lookup"><span data-stu-id="46f46-150">A <xref:System.IDisposable.Dispose%2A> implementation that calls the `Dispose(Boolean)` method.</span></span>  
  
* <span data-ttu-id="46f46-151">执行释放资源的实际工作的 `Dispose(Boolean)` 方法。</span><span class="sxs-lookup"><span data-stu-id="46f46-151">A `Dispose(Boolean)` method that performs the actual work of releasing resources.</span></span>  
  
* <span data-ttu-id="46f46-152">从包装非托管资源的 <xref:System.Runtime.InteropServices.SafeHandle> 派生的类（推荐），或对 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 方法的重写。</span><span class="sxs-lookup"><span data-stu-id="46f46-152">Either a class derived from <xref:System.Runtime.InteropServices.SafeHandle> that wraps your unmanaged resource (recommended), or an override to the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46f46-153"><xref:System.Runtime.InteropServices.SafeHandle> 类提供了一个使你无需编写代码的终结器。</span><span class="sxs-lookup"><span data-stu-id="46f46-153">The <xref:System.Runtime.InteropServices.SafeHandle> class provides a finalizer that frees you from having to code one.</span></span>  
  
<span data-ttu-id="46f46-154">以下是一个常规模式，用于实现使用安全句柄的基类的释放模式：</span><span class="sxs-lookup"><span data-stu-id="46f46-154">Here's the general pattern for implementing the dispose pattern for a base class that uses a safe handle.</span></span>  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="46f46-155">上一个示例使用 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 对象阐释模式；可以使用派生自 <xref:System.Runtime.InteropServices.SafeHandle> 的任何对象来替代。</span><span class="sxs-lookup"><span data-stu-id="46f46-155">The previous example uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to illustrate the pattern; any object derived from <xref:System.Runtime.InteropServices.SafeHandle> could be used instead.</span></span> <span data-ttu-id="46f46-156">请注意，该示例不会正确实例化其 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 对象。</span><span class="sxs-lookup"><span data-stu-id="46f46-156">Note that the example does not properly instantiate its <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object.</span></span>  
  
<span data-ttu-id="46f46-157">以下是一个常规模式，用于实现重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 的基类的释放模式。</span><span class="sxs-lookup"><span data-stu-id="46f46-157">Here's the general pattern for implementing the dispose pattern for a base class that overrides <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.</span></span>  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> <span data-ttu-id="46f46-158">在 C# 中，通过定义[析构函数](~/docs/csharp/programming-guide/classes-and-structs/destructors.md)重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="46f46-158">In C#, you override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> by defining a [destructor](~/docs/csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a><span data-ttu-id="46f46-159">实现派生类的释放模式</span><span class="sxs-lookup"><span data-stu-id="46f46-159">Implementing the dispose pattern for a derived class</span></span>

<span data-ttu-id="46f46-160">从实现 <xref:System.IDisposable> 接口的类派生的类不应实现 <xref:System.IDisposable>，因为 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 的基类实现由其派生类继承。</span><span class="sxs-lookup"><span data-stu-id="46f46-160">A class derived from a class that implements the <xref:System.IDisposable> interface shouldn't implement <xref:System.IDisposable>, because the base class implementation of <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> is inherited by its derived classes.</span></span> <span data-ttu-id="46f46-161">相反，若要实现派生类的释放模式，你可提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="46f46-161">Instead, to implement the dispose pattern for a derived class, you provide the following:</span></span>  
  
* <span data-ttu-id="46f46-162">`protected Dispose(Boolean)` 方法，用于替代基类方法并执行释放派生类的资源的实际工作。</span><span class="sxs-lookup"><span data-stu-id="46f46-162">A `protected Dispose(Boolean)` method that overrides the base class method and performs the actual work of releasing the resources of the derived class.</span></span> <span data-ttu-id="46f46-163">此方法还应调用基类的 `Dispose(Boolean)` 方法并向其传递 *disposing* 参数的 `true` 值。</span><span class="sxs-lookup"><span data-stu-id="46f46-163">This method should also call the `Dispose(Boolean)` method of the base class and pass it a value of `true` for the *disposing* argument.</span></span>  
  
* <span data-ttu-id="46f46-164">从包装非托管资源的 <xref:System.Runtime.InteropServices.SafeHandle> 派生的类（推荐），或对 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 方法的重写。</span><span class="sxs-lookup"><span data-stu-id="46f46-164">Either a class derived from <xref:System.Runtime.InteropServices.SafeHandle> that wraps your unmanaged resource (recommended), or an override to the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46f46-165"><xref:System.Runtime.InteropServices.SafeHandle> 类提供了一个使你无需编写代码的终结器。</span><span class="sxs-lookup"><span data-stu-id="46f46-165">The <xref:System.Runtime.InteropServices.SafeHandle> class provides a finalizer that frees you from having to code one.</span></span> <span data-ttu-id="46f46-166">如果你提供了终结器，则应调用 *disposing* 参数为 `false` 的 `Dispose(Boolean)` 重载。</span><span class="sxs-lookup"><span data-stu-id="46f46-166">If you do provide a finalizer, it should call the `Dispose(Boolean)` overload with a *disposing* argument of `false`.</span></span>  
  
<span data-ttu-id="46f46-167">以下是一个常规模式，用于实现使用安全句柄的派生类的释放模式：</span><span class="sxs-lookup"><span data-stu-id="46f46-167">Here's the general pattern for implementing the dispose pattern for a derived class that uses a safe handle:</span></span>  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="46f46-168">上一个示例使用 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 对象阐释模式；可以使用派生自 <xref:System.Runtime.InteropServices.SafeHandle> 的任何对象来替代。</span><span class="sxs-lookup"><span data-stu-id="46f46-168">The previous example uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to illustrate the pattern; any object derived from <xref:System.Runtime.InteropServices.SafeHandle> could be used instead.</span></span> <span data-ttu-id="46f46-169">请注意，该示例不会正确实例化其 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 对象。</span><span class="sxs-lookup"><span data-stu-id="46f46-169">Note that the example does not properly instantiate its <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object.</span></span>  
  
<span data-ttu-id="46f46-170">以下是一个常规模式，用于实现重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 的派生类的释放模式：</span><span class="sxs-lookup"><span data-stu-id="46f46-170">Here's the general pattern for implementing the dispose pattern for a derived class that overrides <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:</span></span>  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="46f46-171">在 C# 中，通过定义[析构函数](~/docs/csharp/programming-guide/classes-and-structs/destructors.md)重写 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="46f46-171">In C#, you override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> by defining a [destructor](~/docs/csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
<a name="SafeHandles"></a>   
## <a name="using-safe-handles"></a><span data-ttu-id="46f46-172">使用安全句柄</span><span class="sxs-lookup"><span data-stu-id="46f46-172">Using safe handles</span></span>

<span data-ttu-id="46f46-173">编写对象终结器的代码是一项复杂的任务，如果处理不好可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="46f46-173">Writing code for an object's finalizer is a complex task that can cause problems if not done correctly.</span></span> <span data-ttu-id="46f46-174">因此，建议你构造 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 对象，而非实现终结器。</span><span class="sxs-lookup"><span data-stu-id="46f46-174">Therefore, we recommend that you construct <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> objects instead of implementing a finalizer.</span></span>  
  
<span data-ttu-id="46f46-175">从 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 类派生的类通过无中断地分配和释放句柄来简化对象生存期问题。</span><span class="sxs-lookup"><span data-stu-id="46f46-175">Classes derived from the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class simplify object lifetime issues by assigning and releasing handles without interruption.</span></span> <span data-ttu-id="46f46-176">它们包含可以保证在卸载应用程序域时运行的重要终结器。</span><span class="sxs-lookup"><span data-stu-id="46f46-176">They contain a critical finalizer that is guaranteed to run while an application domain is unloading.</span></span> <span data-ttu-id="46f46-177">有关使用安全句柄的优势的更多信息，请参见<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="46f46-177">For more information about the advantages of using a safe handle, see <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46f46-178"><xref:Microsoft.Win32.SafeHandles> 命名空间中的以下派生类提供安全句柄：</span><span class="sxs-lookup"><span data-stu-id="46f46-178">The following derived classes in the <xref:Microsoft.Win32.SafeHandles> namespace provide safe handles:</span></span>  
  
* <span data-ttu-id="46f46-179">用于文件、内存映射文件和管道的 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>、<xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> 和 <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> 类。</span><span class="sxs-lookup"><span data-stu-id="46f46-179">The <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle>, and <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> class, for files, memory mapped files, and pipes.</span></span>  
  
* <span data-ttu-id="46f46-180">用于内存视图的 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 类。</span><span class="sxs-lookup"><span data-stu-id="46f46-180">The <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> class, for memory views.</span></span>  
  
* <span data-ttu-id="46f46-181">用于加密构造的 <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>、<xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> 和 <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> 类。</span><span class="sxs-lookup"><span data-stu-id="46f46-181">The <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle>, and <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> classes, for cryptography constructs.</span></span>  
  
* <span data-ttu-id="46f46-182">用于注册表项的 <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> 类。</span><span class="sxs-lookup"><span data-stu-id="46f46-182">The <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> class, for registry keys.</span></span>  
  
* <span data-ttu-id="46f46-183">用于等待句柄的 <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> 类。</span><span class="sxs-lookup"><span data-stu-id="46f46-183">The <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> class, for wait handles.</span></span>  
  
<a name="base"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a><span data-ttu-id="46f46-184">使用安全句柄实现基类的释放模式</span><span class="sxs-lookup"><span data-stu-id="46f46-184">Using a safe handle to implement the dispose pattern for a base class</span></span>

<span data-ttu-id="46f46-185">下面的示例阐释了基类 `DisposableStreamResource` 的释放模式，此模式使用安全句柄封装非托管资源。</span><span class="sxs-lookup"><span data-stu-id="46f46-185">The following example illustrates the dispose pattern for a base class, `DisposableStreamResource`, that uses a safe handle to encapsulate unmanaged resources.</span></span> <span data-ttu-id="46f46-186">它定义 `DisposableResource` 类，该类使用 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 包装表示打开的文件的 <xref:System.IO.Stream> 对象。</span><span class="sxs-lookup"><span data-stu-id="46f46-186">It defines a `DisposableResource` class that uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> to wrap a <xref:System.IO.Stream> object that represents an open file.</span></span> <span data-ttu-id="46f46-187">`DisposableResource` 方法还包含一个属性 `Size`，该属性返回文件流中的总字节数。</span><span class="sxs-lookup"><span data-stu-id="46f46-187">The `DisposableResource` method also includes a single property, `Size`, that returns the total number of bytes in the file stream.</span></span>  
  
[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a><span data-ttu-id="46f46-188">使用安全句柄实现派生类的释放模式</span><span class="sxs-lookup"><span data-stu-id="46f46-188">Using a safe handle to implement the dispose pattern for a derived class</span></span>

<span data-ttu-id="46f46-189">下面的示例阐释派生类 `DisposableStreamResource2` 的释放模式，该类继承自上一个示例中显示的 `DisposableStreamResource` 类。</span><span class="sxs-lookup"><span data-stu-id="46f46-189">The following example illustrates the dispose pattern for a derived class, `DisposableStreamResource2`, that inherits from the `DisposableStreamResource` class presented in the previous example.</span></span> <span data-ttu-id="46f46-190">此类额外添加一种方法（即 `WriteFileInfo`），并使用 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 对象包装可写文件的句柄。</span><span class="sxs-lookup"><span data-stu-id="46f46-190">The class adds an additional method, `WriteFileInfo`, and uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to wrap the handle of the writable file.</span></span>  
  
[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="46f46-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="46f46-191">See also</span></span>

<span data-ttu-id="46f46-192"><xref:System.GC.SuppressFinalize%2A></span><span class="sxs-lookup"><span data-stu-id="46f46-192"><xref:System.GC.SuppressFinalize%2A></span></span>   
<span data-ttu-id="46f46-193"><xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="46f46-193"><xref:System.IDisposable></span></span>   
<span data-ttu-id="46f46-194"><xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46f46-194"><xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType></span></span>   
<span data-ttu-id="46f46-195"><xref:Microsoft.Win32.SafeHandles></span><span class="sxs-lookup"><span data-stu-id="46f46-195"><xref:Microsoft.Win32.SafeHandles></span></span>   
<span data-ttu-id="46f46-196"><xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46f46-196"><xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType></span></span>   
<span data-ttu-id="46f46-197"><xref:System.Object.Finalize%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46f46-197"><xref:System.Object.Finalize%2A?displayProperty=nameWithType></span></span>   
<span data-ttu-id="46f46-198">[如何：定义和使用类和结构 (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli) </span><span class="sxs-lookup"><span data-stu-id="46f46-198">[How to: Define and Consume Classes and Structs (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli) </span></span>  
[<span data-ttu-id="46f46-199">释放模式</span><span class="sxs-lookup"><span data-stu-id="46f46-199">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)
