---
title: "如何：实现基于事件的异步模式的客户端"
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
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="fc35a-102">如何：实现基于事件的异步模式的客户端</span><span class="sxs-lookup"><span data-stu-id="fc35a-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="fc35a-103">下面的代码示例演示如何使用符合的组件[基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fc35a-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="fc35a-104">此示例中的窗体使用`PrimeNumberCalculator`中所述的组件[如何： 实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="fc35a-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="fc35a-105">运行时使用此示例中的项目，你将看到的"质数计算器"窗体具有网格中，然后两个按钮：**启动新任务**和**取消**。</span><span class="sxs-lookup"><span data-stu-id="fc35a-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="fc35a-106">你可以单击**启动新任务**按钮多次连续，并且每次单击，异步操作将开始的计算来确定随机生成的测试数字是质数。</span><span class="sxs-lookup"><span data-stu-id="fc35a-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="fc35a-107">窗体定期将显示进度和增量结果。</span><span class="sxs-lookup"><span data-stu-id="fc35a-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="fc35a-108">每个操作已分配任务唯一 id。</span><span class="sxs-lookup"><span data-stu-id="fc35a-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="fc35a-109">计算的结果显示在**结果**列; 如果测试数不是主要的则将它标记为**复合，**并显示其第一个除数。</span><span class="sxs-lookup"><span data-stu-id="fc35a-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="fc35a-110">可使用取消任何挂起的操作**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="fc35a-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="fc35a-111">可以进行多个选择。</span><span class="sxs-lookup"><span data-stu-id="fc35a-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc35a-112">大多数数字不是质数。</span><span class="sxs-lookup"><span data-stu-id="fc35a-112">Most numbers will not be prime.</span></span> <span data-ttu-id="fc35a-113">如果你具有在多个已完成操作后未找到的质数，只需启动多个任务，最终你将在其中找到某些质数。</span><span class="sxs-lookup"><span data-stu-id="fc35a-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc35a-114">示例</span><span class="sxs-lookup"><span data-stu-id="fc35a-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="fc35a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc35a-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
