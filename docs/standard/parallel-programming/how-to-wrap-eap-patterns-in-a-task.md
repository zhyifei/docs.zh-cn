---
title: 如何：在任务中包装 EAP 模式
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292bff13b4651b0e886abc435104edfa930f9de1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582764"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="87a19-102">如何：在任务中包装 EAP 模式</span><span class="sxs-lookup"><span data-stu-id="87a19-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="87a19-103">下面的示例演示如何通过使用 <xref:System.Threading.Tasks.TaskCompletionSource%601> 将任意基于事件的异步模式 (EAP) 操作序列公开为一个任务。</span><span class="sxs-lookup"><span data-stu-id="87a19-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="87a19-104">此示例还展示了如何使用 <xref:System.Threading.CancellationToken> 对 <xref:System.Net.WebClient> 对象调用内置的取消方法。</span><span class="sxs-lookup"><span data-stu-id="87a19-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a19-105">示例</span><span class="sxs-lookup"><span data-stu-id="87a19-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="87a19-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="87a19-106">See Also</span></span>  
 [<span data-ttu-id="87a19-107">TPL 和传统 .NET Framework 异步编程</span><span class="sxs-lookup"><span data-stu-id="87a19-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
