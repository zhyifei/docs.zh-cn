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
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>如何：实现基于事件的异步模式的客户端
下面的代码示例演示如何使用符合的组件[基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)。 此示例中的窗体使用`PrimeNumberCalculator`中所述的组件[如何： 实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)。  
  
 运行时使用此示例中的项目，你将看到的"质数计算器"窗体具有网格中，然后两个按钮：**启动新任务**和**取消**。 你可以单击**启动新任务**按钮多次连续，并且每次单击，异步操作将开始的计算来确定随机生成的测试数字是质数。 窗体定期将显示进度和增量结果。 每个操作已分配任务唯一 id。 计算的结果显示在**结果**列; 如果测试数不是主要的则将它标记为**复合，**并显示其第一个除数。  
  
 可使用取消任何挂起的操作**取消**按钮。 可以进行多个选择。  
  
> [!NOTE]
>  大多数数字不是质数。 如果你具有在多个已完成操作后未找到的质数，只需启动多个任务，最终你将在其中找到某些质数。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
