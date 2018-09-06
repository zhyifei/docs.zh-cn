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
ms.openlocfilehash: ff52e17cfe4a4236e4d165c0961ca3a23fed9a72
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864639"
---
# <a name="dispose-pattern"></a><span data-ttu-id="fa6dd-102">释放模式</span><span class="sxs-lookup"><span data-stu-id="fa6dd-102">Dispose Pattern</span></span>
<span data-ttu-id="fa6dd-103">所有程序执行期间都获取一个或多个系统资源，例如内存、 系统句柄或数据库连接。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="fa6dd-104">开发人员必须谨慎使用此类系统资源，因为它们必须发布后已获取并使用。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="fa6dd-105">CLR 提供自动内存管理的支持。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="fa6dd-106">托管内存 (使用 C# 运算符分配的内存`new`) 不需要显式释放。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="fa6dd-107">它是由垃圾回收器 (GC) 自动释放。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="fa6dd-108">这使开发人员不再释放内存的繁琐和困难的任务，并已由.NET Framework 所提供的前所未有的工作效率的主要原因之一。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="fa6dd-109">遗憾的是，托管的内存是只是许多类型的系统资源之一。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="fa6dd-110">非托管内存资源仍需要显式释放和称为非托管资源。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="fa6dd-111">GC 已不专门设计用于管理此类非托管的资源，这意味着，负责管理非托管的资源存在于开发人员手中。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="fa6dd-112">CLR 提供了一些帮助中释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="fa6dd-113"><xref:System.Object?displayProperty=nameWithType> 声明的虚方法<xref:System.Object.Finalize%2A>（也称为终结器） 的 GC 之前调用对象的内存 gc 将被回收，可以重写以释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="fa6dd-114">重写终结器的类型称为可终结的类型。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="fa6dd-115">尽管终结器是在一些清理方案中有效，但它们有两个重大缺点：</span><span class="sxs-lookup"><span data-stu-id="fa6dd-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="fa6dd-116">GC 检测到某个对象符合回收条件时，将调用终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="fa6dd-117">发生这种情况在不确定一段时间后不再需要资源。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="fa6dd-118">当开发人员可以或想要释放的资源和资源由终结器的实际发布时的时间之间的延迟可能是不可接受，或获取许多稀缺资源 （可以轻松地耗尽的资源） 的程序中在其中的资源成本保持在使用 （例如，较大的非托管的内存缓冲区） 的情况。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="fa6dd-119">当 CLR 需要调用终结器时，它必须推迟回收对象的内存，直至下一轮垃圾回收 （集合之间运行终结器）。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="fa6dd-120">这意味着，该对象的内存 （和它引用的所有对象） 将不会释放的时间更长一段。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="fa6dd-121">因此，依赖于终结器以独占方式可能不适用时务必要处理稀缺资源时，尽可能快地回收非托管的资源的许多方案中或在高性能方案中在其中添加了的 GC 开销终止的是不可接受。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="fa6dd-122">该框架提供了<xref:System.IDisposable?displayProperty=nameWithType>应实现以提供开发人员不需要它们时，就立即释放非托管的资源的手动方法的接口。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="fa6dd-123">它还提供了<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>方法来告诉 GC，对象已手动释放的不需要完成，而这种情况下之前回收对象的内存。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="fa6dd-124">类型实现`IDisposable`接口称为可处置类型。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="fa6dd-125">Dispose 模式旨在标准化的使用情况和实现终结器和`IDisposable`接口。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="fa6dd-126">该模式的主要动机是降低实现的复杂性<xref:System.Object.Finalize%2A>和<xref:System.IDisposable.Dispose%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="fa6dd-127">复杂性，是因为方法共享 （更高版本的一章中描述了差异） 的部分而不是所有代码路径。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="fa6dd-128">此外，还有历史原因的确定性资源管理的语言支持不断发展和相关的模式的某些元素。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="fa6dd-129">**✓ DO** 在包含可释放类型的实例的类型上实现基本的释放模式。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="fa6dd-130">请参阅[基本 Dispose 模式](#basic_pattern)部分有关的基本模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="fa6dd-131">如果类型是负责其他可释放对象的生存期，开发人员需要太释放它们，一种方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="fa6dd-132">使用容器的`Dispose`方法是实现此类的简便方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="fa6dd-133">**✓ DO** 实现基本的释放模式，并保持资源需要显式释放和没有终结器类型提供了终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="fa6dd-134">例如，应在存储非托管的内存缓冲区的类型上实现模式。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="fa6dd-135">[可终止类型](#finalizable_types)部分讨论了与实现终结器相关的指导原则。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="fa6dd-136">**✓ CONSIDER** 实现基本的释放模式对类本身不保存非托管资源或可释放的对象但很可能会有执行的子类型。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="fa6dd-137">一个很好的例子是<xref:System.IO.Stream?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="fa6dd-138">虽然很不占用任何资源的抽象基类，但大部分其子类执行操作并因此，它可实现此模式。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="fa6dd-139">基本的释放模式</span><span class="sxs-lookup"><span data-stu-id="fa6dd-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="fa6dd-140">该模式的基本实现涉及到实现`System.IDisposable`接口并声明`Dispose(bool)`方法，实现之间共享的所有资源清理逻辑`Dispose`方法和可选的终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="fa6dd-141">下面的示例演示基本模式的简单实现：</span><span class="sxs-lookup"><span data-stu-id="fa6dd-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
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
  
 <span data-ttu-id="fa6dd-142">布尔参数`disposing`指示是否从调用该方法`IDisposable.Dispose`实现或从终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="fa6dd-143">`Dispose(bool)`实现应在访问其他引用对象 （例如，在前面的示例资源域） 之前检查参数。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="fa6dd-144">从调用方法时，应该只能访问此类对象`IDisposable.Dispose`实现 (当`disposing`参数等于 true)。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="fa6dd-145">如果从终结器调用该方法 (`disposing`为 false)，不应访问其他对象。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="fa6dd-146">原因是对象最终确定之后以不可预知的顺序，因此它们，或任何其依赖项，可能已经完成。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="fa6dd-147">此外，本部分适用于具有未实现 Dispose 模式的基础的类。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="fa6dd-148">如果继承已实现的模式的类时，只需重写`Dispose(bool)`方法以提供更多资源的清理逻辑。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="fa6dd-149">**✓ DO** 声明`protected virtual void Dispose(bool disposing)`方法来集中所有逻辑与释放非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="fa6dd-150">在这种方法应执行所有资源清除。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="fa6dd-151">从这两个终结器调用该方法和`IDisposable.Dispose`方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="fa6dd-152">参数将为 false，如果在终结器内的调用。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="fa6dd-153">它应该用于确保在终止期间运行的任何代码不能访问其他可终结的对象。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="fa6dd-154">下一步部分所述实现终结器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="fa6dd-155">**✓ DO** 实现`IDisposable`接口通过只需调用`Dispose(true)`跟`GC.SuppressFinalize(this)`。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="fa6dd-156">在调用`SuppressFinalize`应仅发生如果`Dispose(true)`成功执行。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="fa6dd-157">**X DO NOT** 进行的无参数`Dispose`虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="fa6dd-158">`Dispose(bool)`方法是应由子类中重写。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
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
  
 <span data-ttu-id="fa6dd-159">**X DO NOT** 声明的任何重载`Dispose`以外的其他方法`Dispose()`和`Dispose(bool)`。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="fa6dd-160">`Dispose` 应考虑以帮助对此模式，防止产生混乱之间实施者、 用户和编译器的保留的字。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="fa6dd-161">某些语言可能会选择自动特定类型上实现此模式。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="fa6dd-162">**✓ DO** 允许`Dispose(bool)`不止一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="fa6dd-163">该方法可以选择在第一次调用后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-163">The method might choose to do nothing after the first call.</span></span>  
  
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
  
 <span data-ttu-id="fa6dd-164">**X AVOID** 内引发异常`Dispose(bool)`除非包含进程已损坏，重要的情况下 （泄漏，不一致的共享的状态，等等。）。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="fa6dd-165">用户希望调用`Dispose`不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="fa6dd-166">如果`Dispose`无法引发了异常，将不会执行进一步的 finally 块清理逻辑。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="fa6dd-167">若要解决此问题，用户需要换行的每个调用`Dispose`(在 finally 块 ！) 在 try 块中，这会导致非常复杂的清理处理程序。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="fa6dd-168">如果执行`Dispose(bool disposing)`方法，永远不会引发的异常，如果释放为 false。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="fa6dd-169">如果在一个终结器上下文内执行，则执行此操作将终止该进程。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="fa6dd-170">**✓ DO** 引发<xref:System.ObjectDisposedException>从该对象已释放的之后不能使用的任何成员。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
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
  
 <span data-ttu-id="fa6dd-171">**✓ CONSIDER** 提供方法`Close()`，除了`Dispose()`，是否关闭的区域中的标准术语。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="fa6dd-172">这样做时，务必确保`Close`实现相同`Dispose`并考虑实现`IDisposable.Dispose`方法显式。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
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
## <a name="finalizable-types"></a><span data-ttu-id="fa6dd-173">可终结的类型</span><span class="sxs-lookup"><span data-stu-id="fa6dd-173">Finalizable Types</span></span>  
 <span data-ttu-id="fa6dd-174">可终结的类型是通过重写终结器，并提供终结代码方式中的扩展了基本的释放模式的类型`Dispose(bool)`方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="fa6dd-175">终结器难以正确，实现主要是因为不能在其执行过程进行了 （通常情况下有效） 假设系统的状态。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="fa6dd-176">应仔细考虑采取以下指导原则。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="fa6dd-177">请注意的一些准则应用不只是个`Finalize`方法，但对任何代码从终结器调用。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="fa6dd-178">对于基本释放以前所定义的模式，这意味着在执行逻辑`Dispose(bool disposing)`时`disposing`参数为 false。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="fa6dd-179">如果基类已是可终止，并实现基本的释放模式，则不应重写`Finalize`试。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="fa6dd-180">相反，应只覆盖`Dispose(bool)`方法以提供更多资源的清理逻辑。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="fa6dd-181">下面的代码演示可终结的类的一个示例：</span><span class="sxs-lookup"><span data-stu-id="fa6dd-181">The following code shows an example of a finalizable type:</span></span>  
  
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
  
 <span data-ttu-id="fa6dd-182">**X AVOID** 进行类型可终止。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="fa6dd-183">请仔细考虑任何情况下，在其中您认为需要终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="fa6dd-184">没有实际成本与使用终结器，从性能和代码复杂性角度来看的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="fa6dd-185">更倾向于使用资源包装器，如<xref:System.Runtime.InteropServices.SafeHandle>封装非托管的资源，在可能的情况，在这种情况下终结器不需要由于包装负责其自己的资源清理。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="fa6dd-186">**X DO NOT** 使值类型可终止。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="fa6dd-187">实际上只有引用类型获取完成由 CLR，并且因此将忽略任何尝试将一个终结器放在值类型上。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="fa6dd-188">C# 和 c + + 编译器强制执行此规则。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="fa6dd-189">**✓ DO** 使类型可终止，如果类型为负责释放非托管的资源不具有其自己的终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="fa6dd-190">在实现终结器时，只需调用`Dispose(false)`内的所有资源清理逻辑，随时随地`Dispose(bool disposing)`方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
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
  
 <span data-ttu-id="fa6dd-191">**✓ DO** 在每个可终止类型上实现基本的释放模式。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="fa6dd-192">这样一种方法来显式执行终结器负责这些相同的资源的确定性清理，类型的用户。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="fa6dd-193">**X DO NOT** 访问在终结器代码路径中，任何可终结对象，因为，它们将已确定的重大风险。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="fa6dd-194">例如，具有对另一个可终结对象 B 的引用可终结对象 A 不能可靠地使用 B 中 A 的终结器，或反之。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="fa6dd-195">（除了紧急终结的弱排序保障） 随机顺序调用终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="fa6dd-196">此外，请注意，在静态变量中存储的对象将获取在特定时间点应用程序域卸载期间或收集时退出进程。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="fa6dd-197">访问可终结对象 （或调用可能会使用静态变量中存储值的静态方法） 是指一个静态变量可能不安全如果<xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType>，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="fa6dd-198">**✓ DO** 使你`Finalize`受保护的方法。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="fa6dd-199">C#、 c + + 和 VB.NET 开发人员不需要担心这一点，因为编译器帮助强制实施此原则。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="fa6dd-200">**X DO NOT** 让的异常转义从终结器逻辑，除外的严重系统故障。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="fa6dd-201">如果从终结器引发异常，CLR 将关闭整个过程 （从.NET Framework 2.0 版)，防止执行和控制的方式被释放的资源的其他终结器。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="fa6dd-202">**✓ CONSIDER** 创建和使用关键可终结对象 (包含对类型层次结构的类型<xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) 的情况下在其中一个终结器绝对必须执行即使在遇到时强制应用程序域卸载和线程中止。</span><span class="sxs-lookup"><span data-stu-id="fa6dd-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="fa6dd-203">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="fa6dd-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fa6dd-204">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="fa6dd-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6dd-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa6dd-205">See also</span></span>

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="fa6dd-206">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="fa6dd-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="fa6dd-207">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="fa6dd-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [<span data-ttu-id="fa6dd-208">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="fa6dd-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
