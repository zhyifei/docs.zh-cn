---
title: Dispose 模式
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: KrzysztofCwalina
ms.openlocfilehash: ee6e9898ae93e2e6628eadec150a3c9c05f5d9c5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147706"
---
# <a name="dispose-pattern"></a>Dispose 模式
所有程序在执行过程中都会获取一个或多个系统资源，例如内存、系统句柄或数据库连接。 开发人员必须谨慎使用此类系统资源，因为必须在获取和使用后释放它们。  
  
 CLR 支持自动内存管理。 托管内存（使用 C# 运算符 `new` 分配的内存）不需要显式释放。 它由垃圾回收器 (GC) 自动释放。 这使开发人员摆脱了释放内存的繁琐而艰巨的任务，并使 .NET Framework 能够提供前所未有的生产力。  
  
 遗憾的是，托管内存只是众多系统资源中的一种。 托管内存之外的资源被称为非托管资源，仍需要显式释放。 GC 不是专门为管理这种非托管资源而设计的，这意味着开发人员需要负责管理非托管资源。  
  
 CLR 在释放非托管资源方面提供了一些帮助。 <xref:System.Object?displayProperty=nameWithType> 声明了一个虚拟方法 <xref:System.Object.Finalize%2A>（也称为终结器），它在 GC 回收对象的内存之前由 GC 调用，并且可以被重写以释放非托管资源。 重写终结器的类型称为可终结类型。  
  
 尽管终结器在某些清理方案中很有效，但它们有两个明显的缺点：  
  
-   当 GC 检测到某个对象符合回收条件时，将调用终结器。 这在不再需要该资源之后的某个不确定的时间段发生。 这种延迟（即开发人员可能或者想要释放资源的时间与终结器实际释放资源的时间之间的延迟）在获取大量稀缺资源（容易被耗尽的资源）的程序中或者在资源的使用会很昂贵（例如，较大的非托管内存缓冲区）的情况下可能是难以接受的。  
  
-   当 CLR 需要调用终结器时，它必须推迟对象内存的回收，直到开始下一轮垃圾回收（终结器在两次回收的间隔期间运行）。 这意味着对象的内存（及其引用的所有对象）不会释放很长时间。  
  
 因此，在处理稀缺资源时，或者在高性能情况下，终结操作的 GC 开销是不可接受的，在很多情况下，尽可能快地回收非托管资源非常重要，完全依赖终结器可能并不合适。  
  
 Framework 提供了 <xref:System.IDisposable?displayProperty=nameWithType> 接口，应实现该接口，以便为开发人员提供一种手动方式，在不再需要非托管资源时立即释放它们。 它还提供了 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> 方法，该方法可以告诉 GC 已手动释放了一个对象，无需再对其执行终结操作，在这种情况下，可以更早地回收对象的内存。 实现 `IDisposable` 接口的类型称为可释放类型。  
  
 Dispose 模式旨在标准化终结器和 `IDisposable` 接口的使用和实现。  
  
 该模式的主要目的是降低 <xref:System.Object.Finalize%2A> 和 <xref:System.IDisposable.Dispose%2A> 方法实现的复杂性。 这种复杂性源于这样一个事实：这些方法共享一些但不是所有的代码路径（这些差异将在本章后面介绍）。 此外，还有一些历史原因，模式中的一些元素与确定性资源管理的语言支持的演变有关。  
  
 **✓ 务必**在包含可释放类型的实例的类型上实现基本的 Dispose 模式。 请参阅[基本 Dispose 模式](#basic_pattern)部分，了解有关基本模式的详细信息。  
  
 如果某个类型负责其他可释放对象的生命周期，则开发人员也需要一种用于释放它们方法。 使用容器的 `Dispose` 方法就是一种实现此操作的便捷方法。  
  
 **✓ 务必**实现基本的 Dispose 模式，并为需要显式释放且没有终结器的占用资源的类型提供终结器。  
  
 例如，应该在存储非托管内存缓冲区的类型上实现该模式。 [可终结的类型](#finalizable_types) 部分讨论了与实现终结器相关的准则。  
  
 **✓ 考虑**在类上实现基本 Dispose 模式，这些类本身并不包含非托管资源或可释放对象，但可能具有包含这些内容的子类型。  
  
 一个很好的例子是 <xref:System.IO.Stream?displayProperty=nameWithType> 类。 尽管它是一个不包含任何资源的抽象基类，但它的大多数子类却包含，因此它可以实现这种模式。  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>基本 Dispose 模式  
 该模式的基本实现涉及实现 `System.IDisposable` 接口并声明 `Dispose(bool)` 方法，该方法实现在 `Dispose` 方法和可选的终结器之间共享的所有资源清理逻辑。  
  
 下面的示例演示基本模式的简单实现：  
  
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
  
 布尔参数 `disposing` 指示是从 `IDisposable.Dispose` 实现还是从终结器调用该方法。 `Dispose(bool)` 实现应在访问其他引用对象之前检查参数（例如，前面示例中的资源字段）。 只有在从 `IDisposable.Dispose` 实现调用该方法时才应访问此类对象（当 `disposing` 参数等于 true 时）。 如果从终结器调用该方法（`disposing` 为 false ），则不应访问其他对象。 原因是对象以不可预测的顺序被终结，因此它们或它们的任何依赖项可能已经被终结了。  
  
 此外，本部分适用于其基尚未实现 Dispose 模式的类。 如果从已经实现该模式的类继承，只需重写 `Dispose(bool)` 方法来提供其他资源清理逻辑即可。  
  
 **✓ 务必**声明 `protected virtual void Dispose(bool disposing)` 方法来集中与释放非托管资源相关的所有逻辑。  
  
 所有资源清理都应该在此方法中进行。 终结器和 `IDisposable.Dispose` 方法都会调用该方法。 如果从终结器内部调用，该参数将为false。 它应该用于确保在清理期间运行的任何代码都不访问其他可终结对象。 实现终结器的细节将在下一节中介绍。  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ 务必**实现 `IDisposable`接口，只需调用 `GC.SuppressFinalize(this)` 前的 `Dispose(true)`。  
  
 应只在 `Dispose(true)` 成功执行时才调用 `SuppressFinalize`。  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X 切忌**将无参数的 `Dispose` 方法设为 virtual。  
  
 `Dispose(bool)` 方法应由子类重写。  
  
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
  
 **X 切忌**声明 `Dispose()` 和 `Dispose(bool)` 以外的 `Dispose` 方法的任何重载。  
  
 `Dispose` 应视为一个保留词，以便编写此模式并防止在实现者、用户和编译者之间产生混淆。 某些语言可能会选择在某些类型上自动实现此模式。  
  
 **✓ 务必**允许多次调用 `Dispose(bool)` 方法。 第一次调用后，该方法可能不执行任何操作。  
  
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
  
 **X 避免**在 `Dispose(bool)` 中引发异常，除非在内部进程已被破坏的严重情况下（泄漏、不一致的共享状态等）。  
  
 用户会预期对 `Dispose` 的调用不会引发异常。  
  
 如果 `Dispose` 可能引发异常，则 finally 代码块的清理逻辑将不会执行。 要解决这个问题，用户需要在 try 代码块中包含每个对 `Dispose` 的调用（在 finally 代码块中！），这会导致清理处理程序非常复杂。 如果执行 `Dispose(bool disposing)` 方法的时候 disposing 为 false，则永远不要引发异常。 如果在终结器上下文中执行的话，这样做将终止进程。  
  
 **✓ 务必**从释放对象后无法使用的任何成员引发 <xref:System.ObjectDisposedException>。  
  
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
  
 **✓ 考虑**除了 `Dispose()` 之外再提供 `Close()` 方法，如果 close 是该区域中的标准术语。  
  
 这样做时，务必确保 `Close` 与 `Dispose` 具有相同的实现并考虑显式实现 `IDisposable.Dispose` 方法。  
  
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
## <a name="finalizable-types"></a>可终结类型  
 可终结类型是通过重写终结器并在 `Dispose(bool)` 方法中提供终结代码路径来扩展基本 Dispose 模式的类型。  
  
 众所周知，终结器难以正确实现，主要是因为无法在执行期间对系统状态做出某些确定的（通常是有效的）假设。 应仔细考虑以下准则。  
  
 请注意，某些准则不仅适用于 `Finalize` 方法，还适用于从终结器调用的任何代码。 在之前定义的基本 Dispose 模式的情况下，这意味着当 `disposing` 参数为 false 时将在 `Dispose(bool disposing)` 内执行逻辑。  
  
 如果基类已经是可终结的并已实现了基本 Dispose 模式，则不应再次重写 `Finalize`。 应仅重写 `Dispose(bool)` 方法来提供额外的资源清理逻辑。  
  
 下面的代码是可终结类型的示例：  
  
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
  
 **X 避免**将类型设置为可终结。  
  
 请仔细考虑任何需要终结器的情况。 从性能和代码复杂性的角度来看，使用终结器的实例会产生实际的成本。 在可能的情况下，首选 <xref:System.Runtime.InteropServices.SafeHandle> 等资源包装器来封装非托管资源，在这种情况下，不再需要终结器，因为包装器负责自己的资源清理。  
  
 **X 切忌**将值类型设置为可终结。  
  
 实际上只有引用类型才会被 CLR 终结，因此对值类型应用终结器的任何尝试都将被忽略。 C# 和 C++ 编译器强制执行此规则。  
  
 **✓ 务必**将类型设置为可终结，如果类型负责释放自身没有终结器的非托管资源。  
  
 实现终结器时，只需调用 `Dispose(false)` 方法并将所有资源清理逻辑放在 `Dispose(bool disposing)` 方法中。  
  
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
  
 **✓ 务必**在每个可终止类型上实现基本的 Dispose 模式。  
  
 这为该类型的用户提供了一种方法，可以显式执行终结器所负责的同一资源的确定性清理。  
  
 **X 切忌**访问终结器代码路径中的任何可终结对象，因为它们很可能已终结。  
  
 例如，如果一个可终结对象 A 具有对另一个可终结对象 B 的引用，则 A 不能在 A 的终结器中可靠地使用 B ，反之亦然。 终结器的调用顺序是随机的（缺少对关键终结的弱排序保证）。  
  
 此外，请注意，在应用程序域卸载期间或退出进程时，将在某些时刻收集存储在静态变量中的对象。 如果 <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> 返回true，则访问用于引用可终结对象的静态变量（或调用可能使用存储在静态变量中的值的静态方法）可能不安全。  
  
 **✓ 务必**使 `Finalize` 方法处于受保护状态。  
  
 C#、C++ 和 VB.NET 开发人员不需要担心这一点，因为编译器有助于强制执行此准则。  
  
 **X 切忌**让异常从终结器逻辑中逃脱，系统关键故障外。  
  
 如果异常是从终结器引发的，CLR 将关闭整个进程（从 .NET Framework 2.0 版开始），从而阻止执行其他终结器和以受控方式释放资源。  
  
 **✓ 考虑**在终结器绝对必须执行的情况下，或甚至面对强制应用程序域卸载和线程中止的情况下，创建和使用关键的可终结对象（具有包含 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> 的类型层次结构的类型）。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [常用设计模型](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [垃圾回收](../../../docs/standard/garbage-collection/index.md)
