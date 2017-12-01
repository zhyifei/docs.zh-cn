---
title: "如何：注册取消请求的回调"
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
helpviewer_keywords: cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85b15ed610d80958ac9d7e3762ac8ea7b781b8d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a>如何：注册取消请求的回调
下面的示例演示如何注册的委托中，将调用时<xref:System.Threading.CancellationToken.IsCancellationRequested%2A>属性变为 true 由于调用<xref:System.Threading.CancellationTokenSource.Cancel%2A>上创建令牌的对象。 使用此技术可取消本地不支持统一取消框架的异步操作，也可取消阻止可能等待异步操作结束的方法。  
  
> [!NOTE]
>  某些情况下，当启用“仅我的代码”后，Visual Studio 会在引发异常的行中断运行并显示一条错误消息，该消息显示“用户代码未处理异常”。 此错误是良性的。 可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。 若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Net.WebClient.CancelAsync%2A> 方法注册为在通过取消标记请求取消时要调用的方法。  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 如果注册回调时已经请求了取消，那么仍然要保证调用回调。 在此特定情况下，如果当前未执行异步操作，则 <xref:System.Net.WebClient.CancelAsync%2A> 方法将不进行任何操作，因此调用此方法始终是安全的。  
  
## <a name="see-also"></a>另请参阅  
 [托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)
