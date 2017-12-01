---
title: "如何：侦听具有等待句柄的取消请求"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>如何：侦听具有等待句柄的取消请求
如果它等待事件接收信号时，被阻止方法，它不能检查取消标记的值并及时响应。 第一个示例演示如何解决此问题，如你正在使用事件时<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>不以本机方式支持统一的取消框架。 第二个示例演示一种更简单的方法，使用<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>，支持统一取消。  
  
> [!NOTE]
>  某些情况下，当启用“仅我的代码”后，Visual Studio 会在引发异常的行中断运行并显示一条错误消息，该消息显示“用户代码未处理异常”。 此错误是良性的。 可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。 若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Threading.ManualResetEvent>来演示如何取消阻止不支持统一的取消的等待句柄。  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Threading.ManualResetEventSlim>来演示如何取消阻止协调基元支持统一取消。 相同的方法可与其他轻型坐标基元，例如<xref:System.Threading.Semaphore>`Slim`和<xref:System.Threading.CountdownEvent>。  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>另请参阅  
 [托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)
