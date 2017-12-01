---
title: "如何：侦听多个取消请求"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>如何：侦听多个取消请求
此示例演示如何同时侦听除外到两个取消标记，以便你可以取消的操作，如果任一令牌请求，则。  
  
> [!NOTE]
>  某些情况下，当启用“仅我的代码”后，Visual Studio 会在引发异常的行中断运行并显示一条错误消息，该消息显示“用户代码未处理异常”。 此错误是良性的。 可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。 若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A>方法用于将两个标记联接成一个令牌。 这使得可以将标记传递给只采用一个取消标记作为参数的方法。 该示例演示一种方法必须在其中观察在传递从外部类，并在类中生成的令牌的这两个标记的常见方案。  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 当链接的令牌引发<xref:System.OperationCanceledException>，传递给此异常的标记是链接的令牌，不是任何一个前置令牌。 若要确定哪些标记已取消，请直接检查前置标记的状态。  
  
 在此示例中，<xref:System.AggregateException>应永远不会引发，但因为此处捕获在实际方案中除以外的任何其他异常<xref:System.OperationCanceledException>从任务委托引发的包装在<xref:System.OperationCanceledException>。  
  
## <a name="see-also"></a>另请参阅  
 [托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)
