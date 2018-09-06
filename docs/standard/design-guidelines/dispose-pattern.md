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
# <a name="dispose-pattern"></a>释放模式
所有程序执行期间都获取一个或多个系统资源，例如内存、 系统句柄或数据库连接。 开发人员必须谨慎使用此类系统资源，因为它们必须发布后已获取并使用。  
  
 CLR 提供自动内存管理的支持。 托管内存 (使用 C# 运算符分配的内存`new`) 不需要显式释放。 它是由垃圾回收器 (GC) 自动释放。 这使开发人员不再释放内存的繁琐和困难的任务，并已由.NET Framework 所提供的前所未有的工作效率的主要原因之一。  
  
 遗憾的是，托管的内存是只是许多类型的系统资源之一。 非托管内存资源仍需要显式释放和称为非托管资源。 GC 已不专门设计用于管理此类非托管的资源，这意味着，负责管理非托管的资源存在于开发人员手中。  
  
 CLR 提供了一些帮助中释放非托管的资源。 <xref:System.Object?displayProperty=nameWithType> 声明的虚方法<xref:System.Object.Finalize%2A>（也称为终结器） 的 GC 之前调用对象的内存 gc 将被回收，可以重写以释放非托管的资源。 重写终结器的类型称为可终结的类型。  
  
 尽管终结器是在一些清理方案中有效，但它们有两个重大缺点：  
  
-   GC 检测到某个对象符合回收条件时，将调用终结器。 发生这种情况在不确定一段时间后不再需要资源。 当开发人员可以或想要释放的资源和资源由终结器的实际发布时的时间之间的延迟可能是不可接受，或获取许多稀缺资源 （可以轻松地耗尽的资源） 的程序中在其中的资源成本保持在使用 （例如，较大的非托管的内存缓冲区） 的情况。  
  
-   当 CLR 需要调用终结器时，它必须推迟回收对象的内存，直至下一轮垃圾回收 （集合之间运行终结器）。 这意味着，该对象的内存 （和它引用的所有对象） 将不会释放的时间更长一段。  
  
 因此，依赖于终结器以独占方式可能不适用时务必要处理稀缺资源时，尽可能快地回收非托管的资源的许多方案中或在高性能方案中在其中添加了的 GC 开销终止的是不可接受。  
  
 该框架提供了<xref:System.IDisposable?displayProperty=nameWithType>应实现以提供开发人员不需要它们时，就立即释放非托管的资源的手动方法的接口。 它还提供了<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>方法来告诉 GC，对象已手动释放的不需要完成，而这种情况下之前回收对象的内存。 类型实现`IDisposable`接口称为可处置类型。  
  
 Dispose 模式旨在标准化的使用情况和实现终结器和`IDisposable`接口。  
  
 该模式的主要动机是降低实现的复杂性<xref:System.Object.Finalize%2A>和<xref:System.IDisposable.Dispose%2A>方法。 复杂性，是因为方法共享 （更高版本的一章中描述了差异） 的部分而不是所有代码路径。 此外，还有历史原因的确定性资源管理的语言支持不断发展和相关的模式的某些元素。  
  
 **✓ DO** 在包含可释放类型的实例的类型上实现基本的释放模式。 请参阅[基本 Dispose 模式](#basic_pattern)部分有关的基本模式的详细信息。  
  
 如果类型是负责其他可释放对象的生存期，开发人员需要太释放它们，一种方法。 使用容器的`Dispose`方法是实现此类的简便方法。  
  
 **✓ DO** 实现基本的释放模式，并保持资源需要显式释放和没有终结器类型提供了终结器。  
  
 例如，应在存储非托管的内存缓冲区的类型上实现模式。 [可终止类型](#finalizable_types)部分讨论了与实现终结器相关的指导原则。  
  
 **✓ CONSIDER** 实现基本的释放模式对类本身不保存非托管资源或可释放的对象但很可能会有执行的子类型。  
  
 一个很好的例子是<xref:System.IO.Stream?displayProperty=nameWithType>类。 虽然很不占用任何资源的抽象基类，但大部分其子类执行操作并因此，它可实现此模式。  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>基本的释放模式  
 该模式的基本实现涉及到实现`System.IDisposable`接口并声明`Dispose(bool)`方法，实现之间共享的所有资源清理逻辑`Dispose`方法和可选的终结器。  
  
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
  
 布尔参数`disposing`指示是否从调用该方法`IDisposable.Dispose`实现或从终结器。 `Dispose(bool)`实现应在访问其他引用对象 （例如，在前面的示例资源域） 之前检查参数。 从调用方法时，应该只能访问此类对象`IDisposable.Dispose`实现 (当`disposing`参数等于 true)。 如果从终结器调用该方法 (`disposing`为 false)，不应访问其他对象。 原因是对象最终确定之后以不可预知的顺序，因此它们，或任何其依赖项，可能已经完成。  
  
 此外，本部分适用于具有未实现 Dispose 模式的基础的类。 如果继承已实现的模式的类时，只需重写`Dispose(bool)`方法以提供更多资源的清理逻辑。  
  
 **✓ DO** 声明`protected virtual void Dispose(bool disposing)`方法来集中所有逻辑与释放非托管的资源。  
  
 在这种方法应执行所有资源清除。 从这两个终结器调用该方法和`IDisposable.Dispose`方法。 参数将为 false，如果在终结器内的调用。 它应该用于确保在终止期间运行的任何代码不能访问其他可终结的对象。 下一步部分所述实现终结器的详细信息。  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ DO** 实现`IDisposable`接口通过只需调用`Dispose(true)`跟`GC.SuppressFinalize(this)`。  
  
 在调用`SuppressFinalize`应仅发生如果`Dispose(true)`成功执行。  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X DO NOT** 进行的无参数`Dispose`虚拟方法。  
  
 `Dispose(bool)`方法是应由子类中重写。  
  
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
  
 **X DO NOT** 声明的任何重载`Dispose`以外的其他方法`Dispose()`和`Dispose(bool)`。  
  
 `Dispose` 应考虑以帮助对此模式，防止产生混乱之间实施者、 用户和编译器的保留的字。 某些语言可能会选择自动特定类型上实现此模式。  
  
 **✓ DO** 允许`Dispose(bool)`不止一次调用方法。 该方法可以选择在第一次调用后不执行任何操作。  
  
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
  
 **X AVOID** 内引发异常`Dispose(bool)`除非包含进程已损坏，重要的情况下 （泄漏，不一致的共享的状态，等等。）。  
  
 用户希望调用`Dispose`不会引发异常。  
  
 如果`Dispose`无法引发了异常，将不会执行进一步的 finally 块清理逻辑。 若要解决此问题，用户需要换行的每个调用`Dispose`(在 finally 块 ！) 在 try 块中，这会导致非常复杂的清理处理程序。 如果执行`Dispose(bool disposing)`方法，永远不会引发的异常，如果释放为 false。 如果在一个终结器上下文内执行，则执行此操作将终止该进程。  
  
 **✓ DO** 引发<xref:System.ObjectDisposedException>从该对象已释放的之后不能使用的任何成员。  
  
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
  
 **✓ CONSIDER** 提供方法`Close()`，除了`Dispose()`，是否关闭的区域中的标准术语。  
  
 这样做时，务必确保`Close`实现相同`Dispose`并考虑实现`IDisposable.Dispose`方法显式。  
  
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
## <a name="finalizable-types"></a>可终结的类型  
 可终结的类型是通过重写终结器，并提供终结代码方式中的扩展了基本的释放模式的类型`Dispose(bool)`方法。  
  
 终结器难以正确，实现主要是因为不能在其执行过程进行了 （通常情况下有效） 假设系统的状态。 应仔细考虑采取以下指导原则。  
  
 请注意的一些准则应用不只是个`Finalize`方法，但对任何代码从终结器调用。 对于基本释放以前所定义的模式，这意味着在执行逻辑`Dispose(bool disposing)`时`disposing`参数为 false。  
  
 如果基类已是可终止，并实现基本的释放模式，则不应重写`Finalize`试。 相反，应只覆盖`Dispose(bool)`方法以提供更多资源的清理逻辑。  
  
 下面的代码演示可终结的类的一个示例：  
  
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
  
 **X AVOID** 进行类型可终止。  
  
 请仔细考虑任何情况下，在其中您认为需要终结器。 没有实际成本与使用终结器，从性能和代码复杂性角度来看的实例相关联。 更倾向于使用资源包装器，如<xref:System.Runtime.InteropServices.SafeHandle>封装非托管的资源，在可能的情况，在这种情况下终结器不需要由于包装负责其自己的资源清理。  
  
 **X DO NOT** 使值类型可终止。  
  
 实际上只有引用类型获取完成由 CLR，并且因此将忽略任何尝试将一个终结器放在值类型上。 C# 和 c + + 编译器强制执行此规则。  
  
 **✓ DO** 使类型可终止，如果类型为负责释放非托管的资源不具有其自己的终结器。  
  
 在实现终结器时，只需调用`Dispose(false)`内的所有资源清理逻辑，随时随地`Dispose(bool disposing)`方法。  
  
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
  
 **✓ DO** 在每个可终止类型上实现基本的释放模式。  
  
 这样一种方法来显式执行终结器负责这些相同的资源的确定性清理，类型的用户。  
  
 **X DO NOT** 访问在终结器代码路径中，任何可终结对象，因为，它们将已确定的重大风险。  
  
 例如，具有对另一个可终结对象 B 的引用可终结对象 A 不能可靠地使用 B 中 A 的终结器，或反之。 （除了紧急终结的弱排序保障） 随机顺序调用终结器。  
  
 此外，请注意，在静态变量中存储的对象将获取在特定时间点应用程序域卸载期间或收集时退出进程。 访问可终结对象 （或调用可能会使用静态变量中存储值的静态方法） 是指一个静态变量可能不安全如果<xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType>，则返回 true。  
  
 **✓ DO** 使你`Finalize`受保护的方法。  
  
 C#、 c + + 和 VB.NET 开发人员不需要担心这一点，因为编译器帮助强制实施此原则。  
  
 **X DO NOT** 让的异常转义从终结器逻辑，除外的严重系统故障。  
  
 如果从终结器引发异常，CLR 将关闭整个过程 （从.NET Framework 2.0 版)，防止执行和控制的方式被释放的资源的其他终结器。  
  
 **✓ CONSIDER** 创建和使用关键可终结对象 (包含对类型层次结构的类型<xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) 的情况下在其中一个终结器绝对必须执行即使在遇到时强制应用程序域卸载和线程中止。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [常用设计模型](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [垃圾回收](../../../docs/standard/garbage-collection/index.md)
