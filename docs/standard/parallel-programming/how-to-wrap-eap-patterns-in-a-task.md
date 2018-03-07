---
title: "如何：在任务中包装 EAP 模式"
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
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9e451c3ce8bb50cb17da7fef25ae0317bcb82c3e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="e0be7-102">如何：在任务中包装 EAP 模式</span><span class="sxs-lookup"><span data-stu-id="e0be7-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="e0be7-103">下面的示例演示如何通过使用 <xref:System.Threading.Tasks.TaskCompletionSource%601> 将任意基于事件的异步模式 (EAP) 操作序列公开为一个任务。</span><span class="sxs-lookup"><span data-stu-id="e0be7-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="e0be7-104">此示例还展示了如何使用 <xref:System.Threading.CancellationToken> 对 <xref:System.Net.WebClient> 对象调用内置的取消方法。</span><span class="sxs-lookup"><span data-stu-id="e0be7-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0be7-105">示例</span><span class="sxs-lookup"><span data-stu-id="e0be7-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="e0be7-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0be7-106">See Also</span></span>  
 [<span data-ttu-id="e0be7-107">TPL 和传统 .NET Framework 异步编程</span><span class="sxs-lookup"><span data-stu-id="e0be7-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
