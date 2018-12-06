---
title: 基于任务的异步模式 (TAP)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 8cef1fcf-6f9f-417c-b21f-3fd8bac75007
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe69943a6f87bbbb7f29d1e4d6d30c26709725d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579010"
---
# <a name="task-based-asynchronous-pattern-tap"></a>基于任务的异步模式 (TAP)
基于任务的异步模式 (TAP) 以 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 命名空间中的 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks?displayProperty=nameWithType> 类型为基础，这些类型用于表示任意异步操作。 对于新的开发项目，建议采用 TAP 作为异步设计模式。  
  
## <a name="naming-parameters-and-return-types"></a>命名、参数和返回类型  
 TAP 使用单个方法表示异步操作的开始和完成。 这与异步编程模型（APM 或 `IAsyncResult`）模式和基于事件的异步模式 (EAP) 不同，APM 要求使用 `Begin` 和 `End` 方法，而 EAP 需要具有 `Async` 后缀的方法，还需要一个或多个事件、事件处理程序委托类型和 `EventArg` 派生类型。 TAP 中的异步方法在操作名称后面添加 `Async` 后缀；例如，`Get` 操作变为 `GetAsync`。 如果要将 TAP 方法添加到一个类中，而该类中已包含带有 `Async` 后缀的相同方法名称，请改用后缀 `TaskAsync`。 例如，如果类中已有 `GetAsync` 方法，请使用名称 `GetTaskAsync`。  
  
 TAP 方法返回 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 或 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>，具体取决于相应同步方法返回的是 void 还是类型 `TResult`。  
  
 TAP 方法的参数应与对应的同步方法匹配，并应以相同顺序提供。  但是，`out` 和 `ref` 参数不受此规则的限制，并应完全避免。 应该将通过 `out` 或 `ref` 参数返回的所有数据改为作为由 `TResult` 返回的 <xref:System.Threading.Tasks.Task%601> 的一部分返回，且应使用元组或自定义数据结构来容纳多个值。 
 
 专用于创建、控制或组合任务的方法无需遵循此命名模式（方法名称或方法所属类型的名称已明确指明方法的异步用途）；此类方法通常称为“组合器”。 组合器的示例包括 <xref:System.Threading.Tasks.Task.WhenAll%2A> 和 <xref:System.Threading.Tasks.Task.WhenAny%2A>，[使用基于任务的异步模式](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)一文的[使用基于任务的内置组合器](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md#combinators)部分对此进行了介绍。  
  
 要通过示例了解 TAP 语法与旧异步编程模式（如异步编程模型 (APM) 和基于事件的异步模式 (EAP)）的语法区别，请参阅[异步编程模式](../../../docs/standard/asynchronous-programming-patterns/index.md)。  
  
## <a name="initiating-an-asynchronous-operation"></a>初始化异步操作  
 基于 TAP 的异步方法可以同步完成少量工作，如在返回结果任务之前，验证自变量和启动异步操作。 应将同步工作量控制在最低范围，确保异步方法可以快速返回。 确保快速返回的理由如下：  
  
-   异步方法可能会从用户界面 (UI) 线程调用；因此，所有长期运行的同步工作都可能会降低应用程序的响应能力。  
  
-   多个异步方法可能会同时启动。 因此，异步方法的同步部分中的任何长时间运行的工作都可能延迟其他异步操作的启动，从而削弱并发的优点。  
  
 在某些情况下，完成操作所需的工作量要比异步启动操作所需的工作量少。 例如，在读取流时使用内存中缓冲的数据来满足读取操作。 在这样的情况下，操作可能会同步完成，并可能返回已完成的任务。  
  
## <a name="exceptions"></a>异常  
 异步方法应该只在响应用法错误的时候，才会在异步方法调用中引发异常。 用法错误任何时候都不应该出现在成品代码中。 例如，如果将 null 引用（在 Visual Basic 中为 `Nothing`）作为某个方法的参数传递导致了错误状态（通常由 <xref:System.ArgumentNullException> 异常表示），则可以修改调用代码以确保绝对不传递 null 引用。 对于所有其他错误，在运行异步方法时发生的异常应分配给返回的任务，即使该异步方法碰巧在任务返回前同步完成。 通常，任务最多包含一个异常。 但是，如果任务表示多个操作（例如，<xref:System.Threading.Tasks.Task.WhenAll%2A>），则多个异常可能与单个任务关联。  
  
## <a name="target-environment"></a>目标环境  
 在实现 TAP 方法时，你可以确定异步执行发生的位置。 你可选择在线程池上执行工作负荷，可选择使用异步 I/O 实现它（不必在大部分操作执行期间绑定到某个线程）或可选择在特定线程（如 UI 线程）上运行它或使用任何数目的潜在上下文。 TAP 方法甚至可能没有要执行的代码，可能只返回 <xref:System.Threading.Tasks.Task> 表示系统其他位置发生的情况（例如，返回一个任务来表示到达队列化数据结构的数据）。
 
 TAP 方法的调用方可能会同步等待生成的任务，以阻止等待 TAP 方法完成，也可能会在异步操作完成时运行其他（延续）代码。 延续代码的创建者可以控制该代码的执行位置。 你可以通过 <xref:System.Threading.Tasks.Task> 类上的方法（例如，<xref:System.Threading.Tasks.Task.ContinueWith%2A>）显式创建延续代码，也可以使用基于延续（例如，C# 中的 `await`、Visual Basic 中的 `Await` 和 F# 中的 `AwaitValue`）构建的语言支持隐式创建延续代码。  
  
## <a name="task-status"></a>任务状态  
 <xref:System.Threading.Tasks.Task> 类提供了异步操作的生命周期，且该周期由 <xref:System.Threading.Tasks.TaskStatus> 枚举表示。 为了支持派生自 <xref:System.Threading.Tasks.Task> 和 <xref:System.Threading.Tasks.Task%601> 的类型的个别案例，并支持构造与调度的分离，<xref:System.Threading.Tasks.Task> 类公开了 <xref:System.Threading.Tasks.Task.Start%2A> 方法。 公共 <xref:System.Threading.Tasks.Task> 构造函数创建的任务称为“冷任务”，因为它们在非计划 <xref:System.Threading.Tasks.TaskStatus.Created> 状态下开始生命周期，并仅在对这些实例调用 <xref:System.Threading.Tasks.Task.Start%2A> 时才被排入计划。 
 
 所有其他任务在热状态下开始其生命周期，这意味着它们表示的异步操作已启动，并且其任务状态是 <xref:System.Threading.Tasks.TaskStatus.Created?displayProperty=nameWithType> 以外的枚举值。 必须激活从 TAP 方法返回的所有任务。 **如果 TAP 方法在内部使用任务的构造函数来实例化要返回的任务，TAP 方法必须在返回前先对 <xref:System.Threading.Tasks.Task> 对象调用 <xref:System.Threading.Tasks.Task.Start%2A>。** TAP 方法的使用者可以安全地假设返回的任务处于活动状态且不应尝试对从 TAP 方法返回的任何 <xref:System.Threading.Tasks.Task> 调用 <xref:System.Threading.Tasks.Task.Start%2A>。 对活动的任务调用 <xref:System.Threading.Tasks.Task.Start%2A> 将引发 <xref:System.InvalidOperationException> 异常。  
  
## <a name="cancellation-optional"></a>取消（可选）  
 在 TAP 中，取消是异步方法实现者和异步方法使用者的选项。 如果操作允许取消，则会公开接受取消标记（<xref:System.Threading.CancellationToken> 实例）的异步方法的重载。 按照约定，该参数命名为 `cancellationToken`。  
  
 [!code-csharp[Conceptual.TAP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#1)]
 [!code-vb[Conceptual.TAP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#1)]  
  
 该异步操作监视此标记以识别取消请求。 如果它收到取消请求，则可以选择接受该请求并取消操作。 如果取消请求导致过早地结束工作，则 TAP 方法返回一个在 <xref:System.Threading.Tasks.TaskStatus.Canceled> 状态下结束的任务；没有可用结果且不引发异常。  <xref:System.Threading.Tasks.TaskStatus.Canceled> 状态被视为任务的最终（完成）状态，<xref:System.Threading.Tasks.TaskStatus.Faulted> 和 <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> 状态同样如此。 因此，如果一个任务处于 <xref:System.Threading.Tasks.TaskStatus.Canceled> 状态，则其 <xref:System.Threading.Tasks.Task.IsCompleted%2A> 属性将返回 `true`。 在 <xref:System.Threading.Tasks.TaskStatus.Canceled> 状态下完成任务时，任务的任何注册延续都将计划或执行，除非指定了 <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled> 之类的延续选项来取消延续。 任何通过使用语言功能异步等待已取消的任务的代码都将继续运行，但会收到 <xref:System.OperationCanceledException> 或从其派生的异常。 通过 <xref:System.Threading.Tasks.Task.Wait%2A> 和 <xref:System.Threading.Tasks.Task.WaitAll%2A> 等方法对该任务进行同步等待的受阻塞的代码也会继续运行并收到异常。  
  
 如果取消标记在接受标记的 TAP 方法被调用之前请求取消，TAP 方法应返回 <xref:System.Threading.Tasks.TaskStatus.Canceled> 任务。  但是，如果在运行异步操作时请求取消，则异步操作不需要接受该取消请求。  仅当操作因为取消请求而结束时，返回的任务才应以 <xref:System.Threading.Tasks.TaskStatus.Canceled> 状态结束。 如果已请求取消，但仍然生成了结果或异常，则任务应在 <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> 或 <xref:System.Threading.Tasks.TaskStatus.Faulted> 状态下结束。 
 
 对于要首先公开取消功能的异步方法，无需提供不接受取消令牌的重载。  对于无法取消的方法，不要提供接受取消标记的重载；这有助于向调用方指示目标方法是否真正可取消。  不要求取消的使用者代码可以调用接受 <xref:System.Threading.CancellationToken> 的方法，并提供 <xref:System.Threading.CancellationToken.None%2A> 作为参数值。 <xref:System.Threading.CancellationToken.None%2A> 在功能上等效于默认 <xref:System.Threading.CancellationToken>。  
  
## <a name="progress-reporting-optional"></a>进度报告（可选）  
 某些异步操作可受益于提供进度通知；这些通知通常用于使用有关该异步操作的进度信息更新用户界面。 
 
 在 TAP 中，通过 <xref:System.IProgress%601> 接口处理进度，此接口作为通常名为 `progress` 的参数传递给异步方法。  调用异步方法时提供进度接口有助于消除不正确使用导致的争用情况（也就是说，操作启动后未正确注册的事件处理程序可能缺少更新）。  更重要的是，进度接口支持不同的进度实现，具体取决于使用代码。  例如，使用代码可能只关心最新的进度更新，可能需要缓冲所有更新，可能需要为各个更新调用操作，也可能需要控制是否需将该调用封送到特定线程。 可以使用接口的不同实现来提供所有这些选项，根据特定使用者的需要进行自定义。  与取消一样，仅在 API 支持进度通知时，TAP 实现才应提供 <xref:System.IProgress%601> 参数。 
 
 例如，如果本文前面所述的 `ReadAsync` 方法可以以到目前为止读取的字节数的形式报告中间进度，则进度回调可能为 <xref:System.IProgress%601> 接口：  
  
 [!code-csharp[Conceptual.TAP#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#2)]
 [!code-vb[Conceptual.TAP#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#2)]  
  
 如果 `FindFilesAsync` 方法返回满足特定搜索模式的所有文件的列表，则进度回调可以对已完成工作的百分比和当前部分结果集进行估计。  可使用元组执行此操作：  
  
 [!code-csharp[Conceptual.TAP#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#3)]
 [!code-vb[Conceptual.TAP#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#3)]  
  
 也可以使用特定于 API 的数据类型执行此操作：  
  
 [!code-csharp[Conceptual.TAP#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#4)]
 [!code-vb[Conceptual.TAP#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#4)]  
  
 在后一种情况下，特殊数据类型通常应加上后缀 `ProgressInfo`。  
  
 如果 TAP 实现提供接受 `progress` 参数的重载，则必须允许该参数成为 `null`，在这种情况下，不会报告任何进度。 TAP 实现应该同步将进度报告到 <xref:System.Progress%601> 对象，使异步方法能够快速提供进度，并允许进度的使用者确定处理信息的最佳方式和位置。 例如，进度实例可以选择将回调封送，并引发有关捕获到的同步上下文的事件。  
  
## <a name="iprogresst-implementations"></a>IProgress\<T> 实现  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 提供单个 <xref:System.IProgress%601> 实现：<xref:System.Progress%601>。 <xref:System.Progress%601> 类的声明方式如下：  
  
```csharp  
public class Progress<T> : IProgress<T>  
{  
    public Progress();  
    public Progress(Action<T> handler);  
    protected virtual void OnReport(T value);  
    public event EventHandler<T> ProgressChanged;  
}  
```  
  
```vb  
Public Class Progress(Of T) : Inherits IProgress(Of T)  
    Public Sub New()  
    Public Sub New(handler As Action(Of T))  
    Protected Overridable Sub OnReport(value As T)  
    Public Event ProgressChanged As EventHandler(Of T>  
End Class  
```  
  
 <xref:System.Progress%601> 的实例公开 <xref:System.Progress%601.ProgressChanged> 事件，此事件在异步操作每次报告进度更新时引发。 实例化 <xref:System.Progress%601.ProgressChanged> 实例后，会在捕获到的 <xref:System.Threading.SynchronizationContext> 对象上引发 <xref:System.Progress%601> 事件。 如果没有可用的同步上下文，则使用针对线程池的默认上下文。 可以向此事件注册处理程序。 为了方便起见，也可将单个处理程序提供给 <xref:System.Progress%601> 构造函数，并且该处理程序的行为与 <xref:System.Progress%601.ProgressChanged> 事件的事件处理程序一样。 异步引发进度更新以避免在执行事件处理程序期间延迟异步操作。 另一个 <xref:System.IProgress%601> 实现可以选择应用不同的语义。  
  
## <a name="choosing-the-overloads-to-provide"></a>选择要提供的重载  
 如果 TAP 实现同时使用可选的 <xref:System.Threading.Tasks.TaskFactory.CancellationToken%2A> 和可选的 <xref:System.IProgress%601> 参数，则可能需要多达四次的重载：  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
public Task MethodNameAsync(…, IProgress<T> progress);   
public Task MethodNameAsync(…,   
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken cancellationToken) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task   
Public MethodNameAsync(…, cancellationToken As CancellationToken,   
                       progress As IProgress(Of T)) As Task  
```  
  
 但是，许多 TAP 实现既没有提供取消功能，也没有进度功能，因此它们只需要一个方法：  
  
```csharp  
public Task MethodNameAsync(…);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
```  
  
 如果 TAP 实现支持取消或进度但不同时支持二者，则 TAP 实现可以提供以下两种重载：  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
  
// … or …  
  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken) As Task  
  
' … or …  
  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task  
```  
  
 如果 TAP 实现同时支持取消和进度，则可以公开所有四个重载。 但它也可以只提供以下两个：  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…,   
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken,   
                       progress As IProgress(Of T)) As Task  
```  
  
 若要弥补缺少的两个中间组合，开发人员可以为 `cancellationToken` 参数传递 <xref:System.Threading.CancellationToken.None%2A> 或默认的 <xref:System.Threading.CancellationToken>，为 `null` 参数传递 `progress`。  
  
 如果需要 TAP 方法的每种用法支持取消或进度，则可以忽略不接受相关参数的重载。  
  
 如果决定公开多个重载以使取消或进度可选，则不支持取消或进度的重载的行为方式应该如同它们已向支持这些选项的重载传递了<xref:System.Threading.CancellationToken.None%2A> 作为取消参数值，`null` 作为进度参数值。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[异步编程模式](../../../docs/standard/asynchronous-programming-patterns/index.md)|介绍执行异步操作的三种模式：基于任务的异步模式 (TAP)、异步编程模型 (APM) 和基于事件的异步模式 (EAP)。|  
|[实现基于任务的异步模式](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)|描述如何使用以下三种方式实现基于任务的异步模式 (TAP)：手动使用 Visual Studio 中的 C# 和 Visual Basic 编译器，或通过编译器和手动方法的组合。|  
|[使用基于任务的异步模式](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)|描述你可以如何使用任务和回调实现等待，而无需阻止。|  
|[与其他异步模式和类型互操作](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)|描述如何使用基于任务的异步模式 (TAP) 实现异步编程模型 (APM) 和基于事件的异步模式 (EAP)。|
