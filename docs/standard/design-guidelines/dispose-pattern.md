---
title: "释放模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e0c2e74afea8a0cb5a0e187f05511eabe0527b90
ms.sourcegitcommit: 08684dd61444c2f072b89b926370f750e456fca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2018
---
# <a name="dispose-pattern"></a>释放模式
所有程序执行过程中都获取一个或多个系统资源，如内存、 系统句柄或数据库连接。 开发人员必须是时使用此类系统资源，请小心，因为它们必须在已获取并使用后释放。  
  
 CLR 提供了对自动内存管理的支持。 管理内存 (使用 C# 运算符分配的内存`new`) 不需要显式释放。 它将在由垃圾回收器 (GC) 自动释放。 这使开发人员释放内存的繁琐和困难的任务，并已由.NET Framework 提供的空前工作效率的主要原因之一。  
  
 遗憾的是，托管的内存是只是其中之一许多类型的系统资源。 非托管内存资源仍需要显式释放并且称为非托管资源。 GC 已专门不用于管理此类非托管的资源，这意味着用于管理非托管的资源的责任在于的开发人员的手中。  
  
 CLR 提供一些帮助中释放非托管的资源。 <xref:System.Object?displayProperty=nameWithType> 声明虚拟方法<xref:System.Object.Finalize%2A>（也称为终结器），由 GC 之前调用对象的内存回收 GC 和可以重写以释放非托管的资源。 重写终结器的类型称为可终结的类型。  
  
 虽然在某些方案中清理有效终结器，但它们具有两个明显的缺点：  
  
-   GC 检测到一个对象符合回收条件时，被调用终结器。 发生这种情况在一些不确定的一段时间后不不再需要该资源。 当开发人员无法或者想要释放资源和资源的终结器的实际发布时的时间之间的延迟可能是不可接受，或获取许多短缺资源 （可以轻松地用完的资源） 的程序中在该资源是成本高昂，以使保持在使用 （例如，较大的非托管的内存缓冲区） 的情况。  
  
-   当 CLR 需要调用终结器时，它必须推迟集合的对象的内存，直至下一个舍入的垃圾回收 （之间集合运行终结器）。 这意味着，该对象的内存 （和它所指向的所有对象） 将不会释放更长的一段时间。  
  
 因此，仅依靠终结器可能不适合在许多情况下很重要短缺资源，在处理时尽快，回收非托管的资源时或在高性能方案在其中添加的 GC 开销终止的是不可接受。  
  
 该框架提供<xref:System.IDisposable?displayProperty=nameWithType>应为提供释放非托管的资源，只要它们不需要的手动方法的开发人员实现的接口。 它还提供了<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>方法可以判断 GC 的对象已手动处理的和不需要完成，在这种情况下可以更早版本回收对象的内存。 类型实现`IDisposable`接口被称为可释放类型。  
  
 释放模式旨在标准化的使用情况和终结器实现与`IDisposable`接口。  
  
 模式的主要动机是降低实现的复杂性<xref:System.Object.Finalize%2A>和<xref:System.IDisposable.Dispose%2A>方法。 复杂性起源于方法共享 （差异介绍的一章中更高版本） 的部分而不是全部代码路径的事实。 此外，还有历史原因的确定性资源管理的语言支持不断发展和相关的模式的某些元素。  
  
 **✓ 执行**在包含可释放类型的实例的类型上实现基本的释放模式。 请参阅[基本的释放模式](#basic_pattern)有关的基本模式的详细信息的部分。  
  
 如果类型为负责其他可释放的对象的生存期，开发人员需要太释放它们，一种方法。 使用容器的`Dispose`方法是一种简便方式做到这一点。  
  
 **✓ 执行**实现基本的释放模式，并保持资源需要显式释放和没有终结器类型提供了终结器。  
  
 例如，应在存储非托管的内存缓冲区的类型上实现此模式。 [可终止类型](#finalizable_types)部分讨论与实现终结器相关的指导原则。  
  
 **请考虑 ✓**实现基本的释放模式对类本身不保存非托管资源或可释放的对象但很可能会有执行的子类型。  
  
 这极好的示例是<xref:System.IO.Stream?displayProperty=nameWithType>类。 虽然很不保留任何资源的抽象基类，但是大部分其子类执行操作，因此，它实现此模式。  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>基本的释放模式  
 模式的基本实现涉及到实现`System.IDisposable`接口，并声明`Dispose(bool)`实现所有资源将清理逻辑之间共享的方法`Dispose`方法和可选的终结器。  
  
 下面的示例演示了基本模式的简单实现：  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder(){  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        if (disposing){  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 布尔参数`disposing`指示方法是否已从调用`IDisposable.Dispose`实现或从终结器。 `Dispose(bool)`实现应在访问其他引用对象 （例如，在前面的示例资源字段） 之前请检查参数。 从调用方法时，应仅以访问此类对象`IDisposable.Dispose`实现 (时`disposing`参数等于 true)。 如果从终结器调用的方法 (`disposing`为 false)，不应访问其他对象。 原因是不可预测的顺序终止对象，因此它们，或任何其依赖项可能已经完成。  
  
 此外，本部分适用于使用未实现 Dispose 模式的基本类。 如果你从已实现的模式的类继承的只需重写`Dispose(bool)`方法以提供其他资源的清理逻辑。  
  
 **✓ 执行**声明`protected virtual void Dispose(bool disposing)`方法来集中所有逻辑与释放非托管的资源。  
  
 所有资源清理应该都出现在此方法。 此方法叫做从这两个终结器和`IDisposable.Dispose`方法。 参数将为 false 如果从中调用在终结器。 它应该用于确保在终止期间运行任何代码不能访问其他可终结的对象。 下一步的部分所述的实现终结器的详细信息。  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ 执行**实现`IDisposable`接口通过只需调用`Dispose(true)`跟`GC.SuppressFinalize(this)`。  
  
 调用`SuppressFinalize`应仅发生如果`Dispose(true)`成功执行。  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X 不**进行的无参数`Dispose`虚拟方法。  
  
 `Dispose(bool)`方法中，是应由子类中被重写。  
  
```  
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
```  
  
 **X 不**声明的任何重载`Dispose`以外的其他方法`Dispose()`和`Dispose(bool)`。  
  
 `Dispose` 应考虑保留的字来帮助 codify 此模式并避免混淆之间实施者、 用户和编译器。 某些语言可能选择自动对于特定类型实现此模式。  
  
 **✓ 执行**允许`Dispose(bool)`不止一次调用方法。 该方法可以选择在第一次调用后不执行任何操作。  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **请避免 x**内引发异常`Dispose(bool)`除非包含进程已损坏，重要的情况下 （泄漏，不一致的共享的状态，等等。）。  
  
 用户期望调用`Dispose`不会引发异常。  
  
 如果`Dispose`无法引发异常，将不执行进一步的 finally 块清理逻辑。 若要解决此问题，用户将需要来包装对每个调用`Dispose`(内 finally 块 ！) 在 try 块，这会导致给非常复杂的清理处理程序。 如果执行`Dispose(bool disposing)`方法，永远不会引发异常; 如果释放为 false。 如果在终结器上下文内执行，则执行此操作将终止进程。  
  
 **✓ 执行**引发<xref:System.ObjectDisposedException>从该对象已释放的之后不能使用的任何成员。  
  
```  
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething(){  
           if(disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
            ...  
    }  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **请考虑 ✓**提供方法`Close()`，除了`Dispose()`，是否关闭的区域中的标准术语。  
  
 当时这样做，务必使您的`Close`实现相同`Dispose`并考虑实现`IDisposable.Dispose`方法显式。  
  
```  
public class Stream : IDisposable {  
    IDisposable.Dispose(){  
        Close();  
    }  
    public void Close(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a>可终止类型  
 可终止类型都是通过重写终结器，并提供终止中的代码路径来扩展基本的释放模式的类型`Dispose(bool)`方法。  
  
 终结器的训练非常困难正确，实现的主要是因为无法在其执行期间进行一些 （通常为有效） 的假设系统的状态。 以下准则应考虑到慎重考虑。  
  
 请注意的一些原则适用不只是于`Finalize`方法，但对任何代码从一个终结器调用。 如果基本释放以前所定义的模式，则这意味着内执行的逻辑`Dispose(bool disposing)`时`disposing`参数为 false。  
  
 如果基的类已是可终止，并实现基本的释放模式，则不应重写`Finalize`试。 相反，应只覆盖`Dispose(bool)`方法以提供其他资源的清理逻辑。  
  
 下面的代码演示可终止类型的一个示例：  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder(){  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing){  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing){ // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **请避免 x**进行类型可终止。  
  
 请仔细考虑在其中你认为终结器所需的任何用例。 没有实际与具有终结器，从性能和代码的复杂性角度实例关联的成本。 喜欢如使用资源包装<xref:System.Runtime.InteropServices.SafeHandle>封装非托管的资源，如果可能，在这种情况下一个终结器变得不必要因为包装负责自己资源清理。  
  
 **X 不**使值类型可终止。  
  
 实际仅引用类型获取完成由 CLR，并因此将忽略任何尝试将一个终结器放在值类型。 C# 和 c + + 编译器强制执行此规则。  
  
 **✓ 执行**使类型可终止，如果类型为负责释放非托管的资源不具有其自己的终结器。  
  
 在实现终结器，只需调用`Dispose(false)`并将中的所有资源的清理逻辑`Dispose(bool disposing)`方法。  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        ...  
    }  
}  
```  
  
 **✓ 执行**在每个可终止类型上实现基本的释放模式。  
  
 这样一种方法来显式执行的终结器负责这些相同的资源的确定性清理进行类型的用户。  
  
 **X 不**访问在终结器代码路径中，任何可终结对象，因为，它们将已确定的重大风险。  
  
 例如，具有到另一个可终结对象 B 引用可终结对象 A 能可靠地使用 B 中 A 的终结器，反之亦然。 按随机顺序 （缺少关键终止的弱排序保障） 调用终结器。  
  
 此外，请注意，对象存储在静态变量将获取在回收中的某些点期间应用程序域卸载或时退出此进程。 访问指的是可终结的对象 （或调用静态方法，可以使用存储在静态变量的值） 的静态变量可能不安全如果<xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType>，则返回 true。  
  
 **✓ 执行**使你`Finalize`受保护的方法。  
  
 C#、 c + + 和 VB.NET 开发人员不需要担心，由于编译器帮助强制实施此原则。  
  
 **X 不**让的异常转义从终结器逻辑，除外的严重系统故障。  
  
 如果从一个终结器引发异常，CLR 将关闭 （截止到.NET Framework 2.0 版)，整个过程阻止执行和从发布以管制方式的资源的其他终结器。  
  
 **✓ 请考虑**创建和使用关键可终结对象 (包含对类型层次结构的类型<xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) 的情况下在其中一个终结器绝对必须执行即使在遇到时强制应用程序域卸载和线程中止。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [常用设计模型](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [垃圾回收](../../../docs/standard/garbage-collection/index.md)
