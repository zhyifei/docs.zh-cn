---
title: 使用 ETW 进行分析跟踪
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a>使用 ETW 进行分析跟踪
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 分析跟踪提供了一种方式来捕获 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务执行过程中的诊断信息。 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 分析跟踪事件是在 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 堆栈中的关键点处发出的，用于在生产环境中排除 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务的故障。 分析跟踪对[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务最小对性能有影响的产品服务器承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)][!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务因为这些事件可以非常高效地发送到 Windows 事件跟踪 (ETW) 会话。  
  
## <a name="in-this-section"></a>本节内容  
 [分析跟踪概述](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 讨论 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 分析跟踪如何处理 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]。  
  
 [动态启用分析跟踪](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 讨论如何使用 ETW 动态启用或禁用跟踪。  
  
 [配置消息流跟踪](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 描述如何配置消息流跟踪。  
  
 [分析跟踪事件参考](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。  
  
## <a name="see-also"></a>请参阅  
 [WCF Services and Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [在 Windows 中将事件跟踪到事件跟踪](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
