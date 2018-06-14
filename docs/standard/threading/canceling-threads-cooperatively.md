---
title: 以协作方式取消线程
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3edd0f9c991df8d8d70b14f4439c5c477e8f1401
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581337"
---
# <a name="canceling-threads-cooperatively"></a>以协作方式取消线程
在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]之前，.NET Framework 不提供内置方法在线程启动以后以协作方式取消线程。 不过，在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中，可以使用取消令牌来取消线程，就像使用它们取消 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 对象或 PLINQ 查询一样。 虽然 <xref:System.Threading.Thread?displayProperty=nameWithType> 类不提供对取消令牌的内置支持，但可以通过需要使用 <xref:System.Threading.ParameterizedThreadStart> 委托的 <xref:System.Threading.Thread> 构造函数，将令牌传递给线程过程。 下面的示例演示如何执行此操作。  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>请参阅  
 [使用线程和线程处理](../../../docs/standard/threading/using-threads-and-threading.md)
