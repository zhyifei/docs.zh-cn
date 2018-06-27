---
title: 释放模式
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7bb9420d6439cff36c5cfa997152773503fbd9a
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948545"
---
# <a name="dispose-pattern"></a><span data-ttu-id="52f89-102">释放模式</span><span class="sxs-lookup"><span data-stu-id="52f89-102">Dispose Pattern</span></span>
<span data-ttu-id="52f89-103">所有程序执行过程中都获取一个或多个系统资源，如内存、 系统句柄或数据库连接。</span><span class="sxs-lookup"><span data-stu-id="52f89-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="52f89-104">开发人员必须是时使用此类系统资源，请小心，因为它们必须在已获取并使用后释放。</span><span class="sxs-lookup"><span data-stu-id="52f89-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="52f89-105">CLR 提供了对自动内存管理的支持。</span><span class="sxs-lookup"><span data-stu-id="52f89-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="52f89-106">管理内存 (使用 C# 运算符分配的内存`new`) 不需要显式释放。</span><span class="sxs-lookup"><span data-stu-id="52f89-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="52f89-107">它将在由垃圾回收器 (GC) 自动释放。</span><span class="sxs-lookup"><span data-stu-id="52f89-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="52f89-108">这使开发人员释放内存的繁琐和困难的任务，并已由.NET Framework 提供的空前工作效率的主要原因之一。</span><span class="sxs-lookup"><span data-stu-id="52f89-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="52f89-109">遗憾的是，托管的内存是只是其中之一许多类型的系统资源。</span><span class="sxs-lookup"><span data-stu-id="52f89-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="52f89-110">非托管内存资源仍需要显式释放并且称为非托管资源。</span><span class="sxs-lookup"><span data-stu-id="52f89-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="52f89-111">GC 已专门不用于管理此类非托管的资源，这意味着用于管理非托管的资源的责任在于的开发人员的手中。</span><span class="sxs-lookup"><span data-stu-id="52f89-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="52f89-112">CLR 提供一些帮助中释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="52f89-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="52f89-113"><xref:System.Object?displayProperty=nameWithType> 声明虚拟方法<xref:System.Object.Finalize%2A>（也称为终结器），由 GC 之前调用对象的内存回收 GC 和可以重写以释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="52f89-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="52f89-114">重写终结器的类型称为可终结的类型。</span><span class="sxs-lookup"><span data-stu-id="52f89-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="52f89-115">虽然在某些方案中清理有效终结器，但它们具有两个明显的缺点：</span><span class="sxs-lookup"><span data-stu-id="52f89-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="52f89-116">GC 检测到一个对象符合回收条件时，被调用终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="52f89-117">发生这种情况在一些不确定的一段时间后不不再需要该资源。</span><span class="sxs-lookup"><span data-stu-id="52f89-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="52f89-118">当开发人员无法或者想要释放资源和资源的终结器的实际发布时的时间之间的延迟可能是不可接受，或获取许多短缺资源 （可以轻松地用完的资源） 的程序中在该资源是成本高昂，以使保持在使用 （例如，较大的非托管的内存缓冲区） 的情况。</span><span class="sxs-lookup"><span data-stu-id="52f89-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="52f89-119">当 CLR 需要调用终结器时，它必须推迟集合的对象的内存，直至下一个舍入的垃圾回收 （之间集合运行终结器）。</span><span class="sxs-lookup"><span data-stu-id="52f89-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="52f89-120">这意味着，该对象的内存 （和它所指向的所有对象） 将不会释放更长的一段时间。</span><span class="sxs-lookup"><span data-stu-id="52f89-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="52f89-121">因此，仅依靠终结器可能不适合在许多情况下很重要短缺资源，在处理时尽快，回收非托管的资源时或在高性能方案在其中添加的 GC 开销终止的是不可接受。</span><span class="sxs-lookup"><span data-stu-id="52f89-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="52f89-122">该框架提供<xref:System.IDisposable?displayProperty=nameWithType>应为提供释放非托管的资源，只要它们不需要的手动方法的开发人员实现的接口。</span><span class="sxs-lookup"><span data-stu-id="52f89-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="52f89-123">它还提供了<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>方法可以判断 GC 的对象已手动处理的和不需要完成，在这种情况下可以更早版本回收对象的内存。</span><span class="sxs-lookup"><span data-stu-id="52f89-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="52f89-124">类型实现`IDisposable`接口被称为可释放类型。</span><span class="sxs-lookup"><span data-stu-id="52f89-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="52f89-125">释放模式旨在标准化的使用情况和终结器实现与`IDisposable`接口。</span><span class="sxs-lookup"><span data-stu-id="52f89-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="52f89-126">模式的主要动机是降低实现的复杂性<xref:System.Object.Finalize%2A>和<xref:System.IDisposable.Dispose%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="52f89-127">复杂性起源于方法共享 （差异介绍的一章中更高版本） 的部分而不是全部代码路径的事实。</span><span class="sxs-lookup"><span data-stu-id="52f89-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="52f89-128">此外，还有历史原因的确定性资源管理的语言支持不断发展和相关的模式的某些元素。</span><span class="sxs-lookup"><span data-stu-id="52f89-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="52f89-129">**✓ 执行**在包含可释放类型的实例的类型上实现基本的释放模式。</span><span class="sxs-lookup"><span data-stu-id="52f89-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="52f89-130">请参阅[基本的释放模式](#basic_pattern)有关的基本模式的详细信息的部分。</span><span class="sxs-lookup"><span data-stu-id="52f89-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="52f89-131">如果类型为负责其他可释放的对象的生存期，开发人员需要太释放它们，一种方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="52f89-132">使用容器的`Dispose`方法是一种简便方式做到这一点。</span><span class="sxs-lookup"><span data-stu-id="52f89-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="52f89-133">**✓ 执行**实现基本的释放模式，并保持资源需要显式释放和没有终结器类型提供了终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="52f89-134">例如，应在存储非托管的内存缓冲区的类型上实现此模式。</span><span class="sxs-lookup"><span data-stu-id="52f89-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="52f89-135">[可终止类型](#finalizable_types)部分讨论与实现终结器相关的指导原则。</span><span class="sxs-lookup"><span data-stu-id="52f89-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="52f89-136">**请考虑 ✓**实现基本的释放模式对类本身不保存非托管资源或可释放的对象但很可能会有执行的子类型。</span><span class="sxs-lookup"><span data-stu-id="52f89-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="52f89-137">这极好的示例是<xref:System.IO.Stream?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="52f89-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="52f89-138">虽然很不保留任何资源的抽象基类，但是大部分其子类执行操作，因此，它实现此模式。</span><span class="sxs-lookup"><span data-stu-id="52f89-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="52f89-139">基本的释放模式</span><span class="sxs-lookup"><span data-stu-id="52f89-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="52f89-140">模式的基本实现涉及到实现`System.IDisposable`接口，并声明`Dispose(bool)`实现所有资源将清理逻辑之间共享的方法`Dispose`方法和可选的终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="52f89-141">下面的示例演示了基本模式的简单实现：</span><span class="sxs-lookup"><span data-stu-id="52f89-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="52f89-142">布尔参数`disposing`指示方法是否已从调用`IDisposable.Dispose`实现或从终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="52f89-143">`Dispose(bool)`实现应在访问其他引用对象 （例如，在前面的示例资源字段） 之前请检查参数。</span><span class="sxs-lookup"><span data-stu-id="52f89-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="52f89-144">从调用方法时，应仅以访问此类对象`IDisposable.Dispose`实现 (时`disposing`参数等于 true)。</span><span class="sxs-lookup"><span data-stu-id="52f89-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="52f89-145">如果从终结器调用的方法 (`disposing`为 false)，不应访问其他对象。</span><span class="sxs-lookup"><span data-stu-id="52f89-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="52f89-146">原因是不可预测的顺序终止对象，因此它们，或任何其依赖项可能已经完成。</span><span class="sxs-lookup"><span data-stu-id="52f89-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="52f89-147">此外，本部分适用于使用未实现 Dispose 模式的基本类。</span><span class="sxs-lookup"><span data-stu-id="52f89-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="52f89-148">如果你从已实现的模式的类继承的只需重写`Dispose(bool)`方法以提供其他资源的清理逻辑。</span><span class="sxs-lookup"><span data-stu-id="52f89-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="52f89-149">**✓ 执行**声明`protected virtual void Dispose(bool disposing)`方法来集中所有逻辑与释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="52f89-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="52f89-150">所有资源清理应该都出现在此方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="52f89-151">此方法叫做从这两个终结器和`IDisposable.Dispose`方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="52f89-152">参数将为 false 如果从中调用在终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="52f89-153">它应该用于确保在终止期间运行任何代码不能访问其他可终结的对象。</span><span class="sxs-lookup"><span data-stu-id="52f89-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="52f89-154">下一步的部分所述的实现终结器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="52f89-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="52f89-155">**✓ 执行**实现`IDisposable`接口通过只需调用`Dispose(true)`跟`GC.SuppressFinalize(this)`。</span><span class="sxs-lookup"><span data-stu-id="52f89-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="52f89-156">调用`SuppressFinalize`应仅发生如果`Dispose(true)`成功执行。</span><span class="sxs-lookup"><span data-stu-id="52f89-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="52f89-157">**X 不**进行的无参数`Dispose`虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="52f89-158">`Dispose(bool)`方法中，是应由子类中被重写。</span><span class="sxs-lookup"><span data-stu-id="52f89-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 <span data-ttu-id="52f89-159">**X 不**声明的任何重载`Dispose`以外的其他方法`Dispose()`和`Dispose(bool)`。</span><span class="sxs-lookup"><span data-stu-id="52f89-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="52f89-160">`Dispose` 应考虑保留的字来帮助 codify 此模式并避免混淆之间实施者、 用户和编译器。</span><span class="sxs-lookup"><span data-stu-id="52f89-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="52f89-161">某些语言可能选择自动对于特定类型实现此模式。</span><span class="sxs-lookup"><span data-stu-id="52f89-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="52f89-162">**✓ 执行**允许`Dispose(bool)`不止一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="52f89-163">该方法可以选择在第一次调用后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="52f89-163">The method might choose to do nothing after the first call.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="52f89-164">**请避免 x**内引发异常`Dispose(bool)`除非包含进程已损坏，重要的情况下 （泄漏，不一致的共享的状态，等等。）。</span><span class="sxs-lookup"><span data-stu-id="52f89-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="52f89-165">用户期望调用`Dispose`不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="52f89-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="52f89-166">如果`Dispose`无法引发异常，将不执行进一步的 finally 块清理逻辑。</span><span class="sxs-lookup"><span data-stu-id="52f89-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="52f89-167">若要解决此问题，用户将需要来包装对每个调用`Dispose`(内 finally 块 ！) 在 try 块，这会导致给非常复杂的清理处理程序。</span><span class="sxs-lookup"><span data-stu-id="52f89-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="52f89-168">如果执行`Dispose(bool disposing)`方法，永远不会引发异常; 如果释放为 false。</span><span class="sxs-lookup"><span data-stu-id="52f89-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="52f89-169">如果在终结器上下文内执行，则执行此操作将终止进程。</span><span class="sxs-lookup"><span data-stu-id="52f89-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="52f89-170">**✓ 执行**引发<xref:System.ObjectDisposedException>从该对象已释放的之后不能使用的任何成员。</span><span class="sxs-lookup"><span data-stu-id="52f89-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="52f89-171">**请考虑 ✓**提供方法`Close()`，除了`Dispose()`，是否关闭的区域中的标准术语。</span><span class="sxs-lookup"><span data-stu-id="52f89-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="52f89-172">当时这样做，务必使您的`Close`实现相同`Dispose`并考虑实现`IDisposable.Dispose`方法显式。</span><span class="sxs-lookup"><span data-stu-id="52f89-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a><span data-ttu-id="52f89-173">可终止类型</span><span class="sxs-lookup"><span data-stu-id="52f89-173">Finalizable Types</span></span>  
 <span data-ttu-id="52f89-174">可终止类型都是通过重写终结器，并提供终止中的代码路径来扩展基本的释放模式的类型`Dispose(bool)`方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="52f89-175">终结器的训练非常困难正确，实现的主要是因为无法在其执行期间进行一些 （通常为有效） 的假设系统的状态。</span><span class="sxs-lookup"><span data-stu-id="52f89-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="52f89-176">以下准则应考虑到慎重考虑。</span><span class="sxs-lookup"><span data-stu-id="52f89-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="52f89-177">请注意的一些原则适用不只是于`Finalize`方法，但对任何代码从一个终结器调用。</span><span class="sxs-lookup"><span data-stu-id="52f89-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="52f89-178">如果基本释放以前所定义的模式，则这意味着内执行的逻辑`Dispose(bool disposing)`时`disposing`参数为 false。</span><span class="sxs-lookup"><span data-stu-id="52f89-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="52f89-179">如果基的类已是可终止，并实现基本的释放模式，则不应重写`Finalize`试。</span><span class="sxs-lookup"><span data-stu-id="52f89-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="52f89-180">相反，应只覆盖`Dispose(bool)`方法以提供其他资源的清理逻辑。</span><span class="sxs-lookup"><span data-stu-id="52f89-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="52f89-181">下面的代码演示可终止类型的一个示例：</span><span class="sxs-lookup"><span data-stu-id="52f89-181">The following code shows an example of a finalizable type:</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 <span data-ttu-id="52f89-182">**请避免 x**进行类型可终止。</span><span class="sxs-lookup"><span data-stu-id="52f89-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="52f89-183">请仔细考虑在其中你认为终结器所需的任何用例。</span><span class="sxs-lookup"><span data-stu-id="52f89-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="52f89-184">没有实际与具有终结器，从性能和代码的复杂性角度实例关联的成本。</span><span class="sxs-lookup"><span data-stu-id="52f89-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="52f89-185">喜欢如使用资源包装<xref:System.Runtime.InteropServices.SafeHandle>封装非托管的资源，如果可能，在这种情况下一个终结器变得不必要因为包装负责自己资源清理。</span><span class="sxs-lookup"><span data-stu-id="52f89-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="52f89-186">**X 不**使值类型可终止。</span><span class="sxs-lookup"><span data-stu-id="52f89-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="52f89-187">实际仅引用类型获取完成由 CLR，并因此将忽略任何尝试将一个终结器放在值类型。</span><span class="sxs-lookup"><span data-stu-id="52f89-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="52f89-188">C# 和 c + + 编译器强制执行此规则。</span><span class="sxs-lookup"><span data-stu-id="52f89-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="52f89-189">**✓ 执行**使类型可终止，如果类型为负责释放非托管的资源不具有其自己的终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="52f89-190">在实现终结器，只需调用`Dispose(false)`并将中的所有资源的清理逻辑`Dispose(bool disposing)`方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 <span data-ttu-id="52f89-191">**✓ 执行**在每个可终止类型上实现基本的释放模式。</span><span class="sxs-lookup"><span data-stu-id="52f89-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="52f89-192">这样一种方法来显式执行的终结器负责这些相同的资源的确定性清理进行类型的用户。</span><span class="sxs-lookup"><span data-stu-id="52f89-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="52f89-193">**X 不**访问在终结器代码路径中，任何可终结对象，因为，它们将已确定的重大风险。</span><span class="sxs-lookup"><span data-stu-id="52f89-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="52f89-194">例如，具有到另一个可终结对象 B 引用可终结对象 A 能可靠地使用 B 中 A 的终结器，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="52f89-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="52f89-195">按随机顺序 （缺少关键终止的弱排序保障） 调用终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="52f89-196">此外，请注意，对象存储在静态变量将获取在回收中的某些点期间应用程序域卸载或时退出此进程。</span><span class="sxs-lookup"><span data-stu-id="52f89-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="52f89-197">访问指的是可终结的对象 （或调用静态方法，可以使用存储在静态变量的值） 的静态变量可能不安全如果<xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType>，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="52f89-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="52f89-198">**✓ 执行**使你`Finalize`受保护的方法。</span><span class="sxs-lookup"><span data-stu-id="52f89-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="52f89-199">C#、 c + + 和 VB.NET 开发人员不需要担心，由于编译器帮助强制实施此原则。</span><span class="sxs-lookup"><span data-stu-id="52f89-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="52f89-200">**X 不**让的异常转义从终结器逻辑，除外的严重系统故障。</span><span class="sxs-lookup"><span data-stu-id="52f89-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="52f89-201">如果从一个终结器引发异常，CLR 将关闭 （截止到.NET Framework 2.0 版)，整个过程阻止执行和从发布以管制方式的资源的其他终结器。</span><span class="sxs-lookup"><span data-stu-id="52f89-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="52f89-202">**✓ 请考虑**创建和使用关键可终结对象 (包含对类型层次结构的类型<xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) 的情况下在其中一个终结器绝对必须执行即使在遇到时强制应用程序域卸载和线程中止。</span><span class="sxs-lookup"><span data-stu-id="52f89-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="52f89-203">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="52f89-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="52f89-204">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="52f89-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f89-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="52f89-205">See Also</span></span>  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="52f89-206">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="52f89-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="52f89-207">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="52f89-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [<span data-ttu-id="52f89-208">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="52f89-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
