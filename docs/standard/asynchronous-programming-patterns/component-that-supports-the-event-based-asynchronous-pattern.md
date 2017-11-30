---
title: "演练：实现支持基于事件的异步模式的组件"
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
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a>演练：实现支持基于事件的异步模式的组件
如果你正在编写具有可能导致显著延迟某些操作的类，请考虑通过实现提供异步功能[基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)。  
  
 本演练阐释了如何创建实现基于事件的异步模式的组件。 使用从帮助程序类实现<xref:System.ComponentModel?displayProperty=nameWithType>命名空间，这样可以确保该组件在任何应用程序模型正确工作，包括[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]，控制台应用程序和 Windows 窗体应用程序。 此组件也是可以用<xref:System.Windows.Forms.PropertyGrid>控制和你自己的自定义设计器。  
  
 完成后，你将具有的应用程序以异步方式计算质数。 你的应用程序将具有主用户界面 (UI) 线程和每个质数计算的线程。 虽然测试是否有大量是质数可能需要花费大量的时间、 通过这种延迟，将不会中断的主 UI 线程和窗体将在计算期间保持响应状态。 你将能够运行，因为许多计算 like 并发并有选择地取消挂起的计算。  
  
 本演练涉及以下任务：  
  
-   创建组件  
  
-   定义公共异步事件和委托  
  
-   定义私有委托  
  
-   实现公共事件  
  
-   实现完成方法  
  
-   实现的辅助方法  
  
-   实现启动和取消方法  
  
 若要将代码复制本主题中的一个单独的清单，请参阅[如何： 实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)。  
  
## <a name="creating-the-component"></a>创建组件  
 第一步是创建将实现基于事件的异步模式的组件。  
  
#### <a name="to-create-the-component"></a>要创建的组件  
  
-   创建一个名为类`PrimeNumberCalculator`继承自<xref:System.ComponentModel.Component>。  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>定义公共异步事件和委托  
 你的组件进行通信使用事件的客户端。 *MethodName* `Completed`事件警报到完成的异步任务，客户端和*MethodName* `ProgressChanged`事件通知的异步任务的进度的客户端。  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>若要为你的组件的客户端定义异步事件：  
  
1.  导入<xref:System.Threading?displayProperty=nameWithType>和<xref:System.Collections.Specialized?displayProperty=nameWithType>在你的文件的顶部的命名空间。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  之前`PrimeNumberCalculator`类定义，声明的进度和完成情况的事件的委托。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  在`PrimeNumberCalculator`类定义中，声明用于报告进度和完成情况向客户端的事件。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  后`PrimeNumberCalculator`类定义中，派生`CalculatePrimeCompletedEventArgs`用于报告的每个客户端的事件处理程序的计算结果的类`CalculatePrimeCompleted`.event。 除了`AsyncCompletedEventArgs`属性，此类使客户端确定测试什么号、 是否是质数，以及内容的第一个约数是如果它不是质数。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>检查点  
 此时，你可以生成组件。  
  
#### <a name="to-test-your-component"></a>若要测试你的组件  
  
-   编译该组件。  
  
     你将收到两个编译器警告：  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     在下一部分中，将清除这些警告。  
  
## <a name="defining-private-delegates"></a>定义私有委托  
 异步方面`PrimeNumberCalculator`组件均与特殊的委托名为在内部实现<xref:System.Threading.SendOrPostCallback>。 A<xref:System.Threading.SendOrPostCallback>表示执行的回调方法<xref:System.Threading.ThreadPool>线程。 回调方法必须具有采用类型的单个参数的签名<xref:System.Object>，这意味着你将需要将传递委托中的包装类之间的状态。 有关详细信息，请参阅<xref:System.Threading.SendOrPostCallback>。  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>若要实现组件的内部异步行为：  
  
1.  声明和创建<xref:System.Threading.SendOrPostCallback>委托中`PrimeNumberCalculator`类。 创建<xref:System.Threading.SendOrPostCallback>实用程序方法中的对象调用`InitializeDelegates`。  
  
     你将需要两个委托： 一个用于向客户端，报告进度，一个用于向客户端报告完成。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  调用`InitializeDelegates`组件的构造函数中的方法。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  在声明委托`PrimeNumberCalculator`处理以异步方式执行的实际工作的类。 此委托包装用于测试是否数字是质数的辅助方法。 委托采用<xref:System.ComponentModel.AsyncOperation>参数，它将用于跟踪异步操作的生存期。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  创建用于管理挂起的异步操作的生存期的集合。 客户端需要跟踪的操作，当它们是执行和完成，但这种跟踪完成通过要求客户端时要传递的唯一令牌或任务 ID、 客户端发出对异步方法的调用的方法。 `PrimeNumberCalculator`组件必须跟踪的每个调用通过使用其相应的调用将任务 ID 相关联。 如果客户端传递不唯一，任务 ID`PrimeNumberCalculator`组件必须引发一个异常。  
  
     `PrimeNumberCalculator`组件将跟踪的任务 ID，通过使用特殊的集合类调用<xref:System.Collections.Specialized.HybridDictionary>。 在类定义中，创建<xref:System.Collections.Specialized.HybridDictionary>调用`userTokenToLifetime`。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>实现公共事件  
 向客户端使用事件通知实现基于事件的异步模式的组件。 上的帮助合适的线程调用这些事件<xref:System.ComponentModel.AsyncOperation>类。  
  
#### <a name="to-raise-events-to-your-components-clients"></a>若要引发事件，以便将您的组件的客户端：  
  
1.  实现用于向客户端报告的公共事件。 你将需要为报告进度和一个用于报告完成事件。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>实现完成方法  
 完成委托是通过成功完成、 错误或取消的异步操作结束时，将调用的基础，自由线程的异步行为的方法。 此调用任意线程上发生的情况。  
  
 此方法是从内部集合的唯一客户端令牌删除客户端的任务 ID 的情况。 此方法也会通过调用结束特定的异步操作的生存期<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>到相应方法<xref:System.ComponentModel.AsyncOperation>。 此调用引发适合于应用程序模型的线程上完成事件。 后<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>调用方法时，此实例的<xref:System.ComponentModel.AsyncOperation>不再使用，并将任何后续尝试使用它将引发异常。  
  
 `CompletionMethod`签名必须包含描述异步操作的结果所需的所有状态。 它包含此特定的异步操作，进行了测试的数量的状态是否为质数和其第一个除数的值如果它不是一个质数数字。 它还包含描述发生的任何异常的状态和<xref:System.ComponentModel.AsyncOperation>对应于此特定任务。  
  
#### <a name="to-complete-an-asynchronous-operation"></a>若要完成一个异步操作：  
  
-   实现完成方法。 它采用六个参数，它用于填充`CalculatePrimeCompletedEventArgs`通过客户端的客户端返回`CalculatePrimeCompletedEventHandler`。 它会从内部的集合中，删除客户端的任务 ID 标记和结束异步操作的整个生存期内通过调用<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>。 <xref:System.ComponentModel.AsyncOperation>封送到的线程或上下文适合于应用程序模型的调用。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>检查点  
 此时，你可以生成组件。  
  
#### <a name="to-test-your-component"></a>若要测试你的组件  
  
-   编译该组件。  
  
     你将收到一个编译器警告：  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     此警告将在下一节中解析。  
  
## <a name="implementing-the-worker-methods"></a>实现的辅助方法  
 到目前为止，已实现的支持异步代码`PrimeNumberCalculator`组件。 现在你可以实现执行的实际工作的代码。 将实现以下三种方法： `CalculateWorker`， `BuildPrimeNumberList`，和`IsPrime`。 在一起，`BuildPrimeNumberList`和`IsPrime`构成调用选筛的埃拉托色尼斯，用于确定数字是质数通过查找最多的测试数的平方根的所有质数的已知算法。 如果没有发现任何约数，通过该点，则测试数为质数。  
  
 如果此组件专为最大效率，则它应记住发现的各种调用不同的测试号码的所有质数。 它还会检查最小的约数，例如 2、 3 和 5。 此示例的目的是为了演示如何耗时的操作可以异步执行，但是，以便为你保留为练习这些优化。  
  
 `CalculateWorker`方法包装在一个委托，并通过调用以异步方式调用`BeginInvoke`。  
  
> [!NOTE]
>  进度报告中实现`BuildPrimeNumberList`方法。 快速在计算机上，`ProgressChanged`可以快速连续引发事件。 客户端线程，在其会引发这些事件，必须能够处理这种情况。 用户界面代码可能是溢满消息和无法保持同步，结果导致挂起行为。 对于示例用户接口处理这种情况下，请参阅[如何： 实现基于事件的异步模式的客户端](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)。  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>以异步方式执行的质数计算：  
  
1.  实现`TaskCanceled`的实用工具方法。 此检查任务生存期集合中是否存在给定的任务 ID，并返回`true`如果找不到任务 ID。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  实现 `CalculateWorker` 方法。 它采用两个参数： 一个数字以测试，请与<xref:System.ComponentModel.AsyncOperation>。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  实现 `BuildPrimeNumberList`。 它采用两个参数： 的编号，以测试，和<xref:System.ComponentModel.AsyncOperation>。 它使用<xref:System.ComponentModel.AsyncOperation>来报告进度和增量结果。 这可确保适当线程或应用程序模型的上下文调用客户端的事件处理程序。 当`BuildPrimeNumberList`质数找到，它报告增量结果给客户端的事件处理程序`ProgressChanged`事件。 这需要从派生的类<xref:System.ComponentModel.ProgressChangedEventArgs>、 调用`CalculatePrimeProgressChangedEventArgs`，该类有一个新增属性调用`LatestPrimeNumber`。  
  
     `BuildPrimeNumberList`方法还会定期调用`TaskCanceled`方法，如果该方法返回的退出`true`。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  实现 `IsPrime`。 它采用三个参数： 已知的质数、 的编号，以测试和找到的第一个约数一个输出参数的列表。 给定的质数列表，它确定测试数是否质数。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  派生`CalculatePrimeProgressChangedEventArgs`从<xref:System.ComponentModel.ProgressChangedEventArgs>。 此类是用于向客户端的事件处理程序报告增量结果必要`ProgressChanged`事件。 它具有一个名为的添加的属性`LatestPrimeNumber`。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>检查点  
 此时，你可以生成组件。  
  
#### <a name="to-test-your-component"></a>若要测试你的组件  
  
-   编译该组件。  
  
     所有这些剩下编写是启动和取消异步操作，方法`CalculatePrimeAsync`和`CancelAsync`。  
  
## <a name="implementing-the-start-and-cancel-methods"></a>实现启动和取消方法  
 通过调用的辅助方法启动其自身线程上`BeginInvoke`上将其包装的委托。 若要管理特定的异步操作的生存期，请调用<xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>方法<xref:System.ComponentModel.AsyncOperationManager>帮助器类。 这将返回<xref:System.ComponentModel.AsyncOperation>，这将封送到合适的线程或上下文调用客户端的事件处理程序。  
  
 通过调用取消挂起操作特定<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>其相应<xref:System.ComponentModel.AsyncOperation>。 这会结束该操作和对任何后续调用其<xref:System.ComponentModel.AsyncOperation>将引发异常。  
  
#### <a name="to-implement-start-and-cancel-functionality"></a>若要实现启动和取消功能：  
  
1.  实现 `CalculatePrimeAsync` 方法。 请确保客户端提供令牌 (任务 ID) 是唯一的表示当前挂起任务的所有标记。 如果客户端传递在非唯一令牌中，`CalculatePrimeAsync`引发异常。 否则，该令牌添加到任务 ID 集合。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  实现 `CancelAsync` 方法。 如果`taskId`参数在令牌的集合中存在，则将删除。 这可以阻止尚未开始运行的已取消的任务。 如果该任务正在运行，`BuildPrimeNumberList`方法退出时检测到的任务 ID 已从生存期集合中移除。  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>检查点  
 此时，你可以生成组件。  
  
#### <a name="to-test-your-component"></a>若要测试你的组件  
  
-   编译该组件。  
  
 `PrimeNumberCalculator`组件现在已完成并可供使用。  
  
 有关使用一个示例客户端`PrimeNumberCalculator`组件，请参阅[如何： 实现基于事件的异步模式的客户端](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)。  
  
## <a name="next-steps"></a>后续步骤  
 你可以填写此示例通过编写`CalculatePrime`，同步等效于`CalculatePrimeAsync`方法。 这将使`PrimeNumberCalculator`完全符合基于事件的异步模式的组件。  
  
 您可以通过保留的发现的各种调用不同的测试号码的所有质数列表来改进此示例。 使用此方法，每个任务将受益于完成前面的任务的工作。 小心地将其保护与此列表`lock`区域，以便序列化到不同的线程列表的访问。  
  
 您还可以进行测试，以最小的约数，例如 2、 3 和 5 改善此示例。  
  
## <a name="see-also"></a>另请参阅  
 [如何：在后台运行操作](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [不在生成中： Visual Basic 中的多线程处理](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [如何：实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [使用基于事件的异步模式进行多线程编程](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
