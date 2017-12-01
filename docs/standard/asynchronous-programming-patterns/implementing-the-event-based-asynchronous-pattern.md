---
title: "实现基于事件的异步模式"
ms.custom: 
ms.date: 03/30/2017
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
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b4df5e4df914d932c7413e9330e8663753456c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a>实现基于事件的异步模式
如果你正在编写的类具有一些可能会带来明显延迟的操作，请考虑实施[基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)中的操作，为该类提供异步功能。  
  
 基于事件的异步模式提供了打包具有异步功能的类的标准化方式。 如果使用的帮助器类实施的例如<xref:System.ComponentModel.AsyncOperationManager>，你的类将任何应用程序在模式下，会正常工作包括[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]，控制台应用程序和 Windows 窗体应用程序。  
  
 有关实现基于事件的异步模式的示例，请参阅[如何：实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)。  
  
 对于简单的异步操作，你可能会发现<xref:System.ComponentModel.BackgroundWorker>合适的组件。 有关详细信息<xref:System.ComponentModel.BackgroundWorker>，请参阅[如何： 在后台运行操作](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)。  
  
 以下列表介绍本主题中讨论的基于事件的异步模式的功能。  
  
-   实现基于事件的异步模式的时机  
  
-   命名异步方法  
  
-   选择性地支持取消  
  
-   选择性地支持 IsBusy 属性  
  
-   选择性地为进度报告提供支持  
  
-   选择性地为返回增量结果提供支持  
  
-   处理方法中的 Out 和 Ref 参数  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>实现基于事件的异步模式的时机  
 请在以下情况下，考虑实现基于事件的异步模式：  
  
-   类的客户端不需要<xref:System.Threading.WaitHandle>和<xref:System.IAsyncResult>对象可用于异步操作，这意味着该轮询和<xref:System.Threading.WaitHandle.WaitAll%2A>或<xref:System.Threading.WaitHandle.WaitAny%2A>需要构建客户端。  
  
-   你希望异步操作由客户端使用常见的事件/委托模型进行托管。  
  
 对于异步实现，任何操作都是候选项，但应优先考虑预计会产生较长延迟的操作。 最适合的操作是客户端在其中调用方法，并在完成时收到通知，无需进一步的干预。 其次是连续运行、定期向客户端通知进度、增量结果和状态更改的操作。  
  
 若要深入了解决定何时支持基于事件的异步模式，请参阅[决定何时实现基于事件的异步模式](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)。  
  
## <a name="naming-asynchronous-methods"></a>命名异步方法  
 对于要向其提供异步等效方法的每个同步方法 *MethodName*：  
  
 定义满足以下条件的 *MethodName*`Async` 方法：  
  
-   返回 `void`。  
  
-   采用与 *MethodName* 方法相同的参数。  
  
-   接受多个调用。  
  
 选择性地定义一个与 *MethodName*`Async` 相同的 *MethodName*`Async`重载，但是让它带有一个附加的对象赋值的参数（即 `userState`）。 如果已准备好管理方法的多个并发调用（在这种情况下，`userState` 值将传递回所有事件处理程序以区分方法的调用），可使用此方法。 也可以选择将其简单地作为存储用户状态以供以后检索的位置。  
  
 对于每个单独的 *MethodName*`Async` 方法签名：  
  
1.  在与方法相同的类中定义以下事件：  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  定义以下委托和<xref:System.ComponentModel.AsyncCompletedEventArgs>。 这些可能会在类本身之外、但在相同命名空间中定义。  
  
    ```vb  
    Public Delegate Sub MethodNameCompletedEventHandler( _  
        ByVal sender As Object, _  
        ByVal e As MethodNameCompletedEventArgs)  
  
    Public Class MethodNameCompletedEventArgs  
        Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As MyReturnType  
    End Property  
    ```  
  
    ```csharp  
    public delegate void MethodNameCompletedEventHandler(object sender,   
        MethodNameCompletedEventArgs e);  
  
    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
    {  
        public MyReturnType Result { get; }  
    }  
    ```  
  
    -   确保 *MethodName*`CompletedEventArgs` 类将其成员公开为只读属性而不是字段，因为字段会阻止数据绑定。  
  
    -   未定义任何<xref:System.ComponentModel.AsyncCompletedEventArgs>-派生不会产生结果的方法的类。 只需使用的实例<xref:System.ComponentModel.AsyncCompletedEventArgs>本身。  
  
        > [!NOTE]
        >  在可行且适当，若要重复使用委托时，它是完全可以接受，和<xref:System.ComponentModel.AsyncCompletedEventArgs>类型。 在这种情况下，命名将不为一致替换的方法名称，因为给定的委托和<xref:System.ComponentModel.AsyncCompletedEventArgs>不依赖于单个方法。  
  
## <a name="optionally-support-cancellation"></a>选择性地支持取消  
 如果你的类将支持取消异步操作，则应向客户端公开取消（如下所述）。 请注意，定义取消支持之前，需要确定两点：  
  
-   你的类（包括将来预计要添加的内容），是否只具有一个支持取消操作的异步操作？  
  
-   支持取消的异步操作是否能支持多个挂起操作？ 即 *MethodName*`Async` 方法是否采用 `userState` 参数？它是否允许在等待任何操作完成之前进行多个调用？  
  
 使用下表中的两个问题的答案来确定取消方法的签名。  
  
### <a name="visual-basic"></a>Visual Basic  
  
||支持多个并行操作|每次一个操作|  
|------|------------------------------------------------|----------------------------------|  
|整个类中具有一个异步操作|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|类中具有多个异步操作|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>C#  
  
||支持多个并行操作|每次一个操作|  
|------|------------------------------------------------|----------------------------------|  
|整个类中具有一个异步操作|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|类中具有多个异步操作|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 如果定义了 `CancelAsync(object userState)` 方法，客户端在选择状态值时必须小心，以使其能够区分对象上调用的所有异步方法，而不仅仅是在单个异步方法的所有调用之间进行区分。  
  
 命名单个异步操作版本 *MethodName*`AsyncCancel` 的决定取决于能否在类似于 Visual Studio 的 IntelliSense 设计环境中更轻松地发现方法。 这会对相关的成员进行分组，将与异步功能无关的其他成员区分开来。 如果预计可能在后续版本中添加其他异步操作，最好定义 `CancelAsync`。  
  
 请勿在同一类中定义上表中的多个方法。 这将毫无意义，或者会由于方法的泛滥而使类接口变得混乱。  
  
 通常，这些方法会立即返回，并且操作实际上可能会/无法取消。 在 *MethodName*`Completed` 事件的事件处理程序中，*MethodName*`CompletedEventArgs` 对象包含 `Cancelled` 字段，客户端可使用该字段来确定是否取消了操作。  
  
 请遵守[实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)中所述的取消语义。  
  
## <a name="optionally-support-the-isbusy-property"></a>选择性地支持 IsBusy 属性  
 如果你的类不支持多个并发调用，请考虑公开 `IsBusy` 属性。 这可以使开发人员确定 *MethodName*`Async` 方法是否不用捕捉 *MethodName*`Async` 方法中的异常就能运行。  
  
 请遵守[实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)中所述的 `IsBusy` 语义。  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>选择性地为进度报告提供支持  
 通常期望异步操作在其操作期间报告进度。 基于事件的异步模式提供了执行此操作的准则。  
  
-   还可以选择性地定义由异步操作引发并在相应线程上调用的事件。 <xref:System.ComponentModel.ProgressChangedEventArgs>对象携带应为介于 0 和 100 之间的整数值的进度指示器。  
  
-   按照以下规则命名此事件：  
  
    -   如果类具有多个异步操作（或预期将来版本中会包括多个异步操作），则命名为 `ProgressChanged`；  
  
    -   如果类具有单一异步操作，则命名为 *MethodName* `ProgressChanged`。  
  
     该命名方法与命名取消方法（如“选择性地支持取消”部分所述）相同。  
  
 应使用此事件<xref:System.ComponentModel.ProgressChangedEventHandler>委托签名和<xref:System.ComponentModel.ProgressChangedEventArgs>类。 或者，如果 （对于实例、 读取的字节和下载操作的总字节数），可以提供更特定于域进度指示器，则您应定义的派生的类<xref:System.ComponentModel.ProgressChangedEventArgs>。  
  
 请注意，无论该类支持多少个异步方法，都只有一个 `ProgressChanged` 或 *MethodName*`ProgressChanged` 事件。 客户端需要使用传递给 *MethodName*`Async` 方法的 `userState` 对象以区分多个并发操作上的进度更新。  
  
 可能出现多个操作支持进度，并且每个操作返回不同的进度指示器的情况。 在这种情况下，不合适支持单个 `ProgressChanged` 事件，你可能需要考虑支持多个 `ProgressChanged` 事件。 在这种情况下，为每个 *MethodName*`Async` 方法使用 *MethodName*`ProgressChanged` 的命名模式。  
  
 请遵守[实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)中所述的进度报告语义。  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>选择性地为返回增量结果提供支持  
 有时异步操作可以在完成之前返回增量结果。 可以通过多种方式支持此方案。 下面是一些示例。  
  
### <a name="single-operation-class"></a>单一操作类  
 如果你的类仅支持单一异步操作，并且能够返回增量结果，则可以：  
  
-   扩展<xref:System.ComponentModel.ProgressChangedEventArgs>类型以承载增量结果数据，并定义*MethodName* `ProgressChanged`与此扩展数据的事件。  
  
-   存在要报告的增量结果时，会引发此 *MethodName*`ProgressChanged` 事件。  
  
 此解决方案特别适用于单一异步操作类，因为发生的同一事件可以返回“所有操作”上的增量结果，与 *MethodName*`ProgressChanged` 事件的作用相同。  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>使用同类增量结果的多操作类  
 在这种情况下，你的类支持多个异步方法，每个方法都能够返回增量结果，并且这些增量结果具有相同的数据类型。  
  
 遵循上文所述的单个操作类，作为相同模型<xref:System.EventArgs>结构将适用于所有增量结果。 定义一个 `ProgressChanged` 事件，而不是 *MethodName*`ProgressChanged` 事件，因为它适用于多个异步方法。  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>使用不同类增量结果的多操作类  
 如果你的类支持多个异步方法，每个方法返回不同类型的数据，则应该：  
  
-   将增量结果报告与进度报告分开。  
  
-   定义单独*MethodName* `ProgressChanged`与相应的事件<xref:System.EventArgs>为每个异步方法以处理该方法的增量结果数据。  
  
 按照[实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)所述，在适当线程上调用事件处理程序。  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>处理方法中的 Out 和 Ref 参数  
 虽然一般情况下，建议不要在 .NET Framework 中使用 `out` 和 `ref`但以下是使用它们时要遵循的规则：  
  
 给定同步方法 *MethodName*：  
  
-   *MethodName* 的 `out` 参数不应为 *MethodName*`Async` 的一部分。 它们应是与 *MethodName* 中的等效参数使用相同名称的 *MethodName*`CompletedEventArgs` 的一部分（除非有更合适的名称）。  
  
-   *MethodName*的 `ref` 参数应显示为 *MethodName*`Async` 的一部分，并且是与 *MethodName* 中的等效参数使用相同名称的 *MethodName*`CompletedEventArgs` 的一部分（除非有更合适的名称）。  
  
 例如，给定：  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 异步方法并将其<xref:System.ComponentModel.AsyncCompletedEventArgs>类将如下所示：  
  
```vb  
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)  
  
Public Class MethodNameCompletedEventArgs  
    Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As Integer   
    End Property  
    Public ReadOnly Property Arg2() As String   
    End Property  
    Public ReadOnly Property Arg3() As String   
    End Property  
End Class  
```  
  
```csharp  
public void MethodNameAsync(string arg1, string arg2);  
  
public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
{  
    public int Result { get; };  
    public string Arg2 { get; };  
    public string Arg3 { get; };  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <xref:System.ComponentModel.AsyncCompletedEventArgs>  
 [如何：实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [如何：在后台运行操作](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [如何：实现使用后台操作的窗体](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [确定何时实现基于事件的异步模式](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 [使用基于事件的异步模式进行多线程编程](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
